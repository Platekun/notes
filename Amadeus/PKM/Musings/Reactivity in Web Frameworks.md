---
Note Type: "Literature"
Author: "Tan Li Hau"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:50 AM"
Sources: "Reactivity in Web Frameworks, Reactivity in Web Frameworks (Part 2) (../Sources/Reactivity%20in%20Web%20Frameworks%20%20c894202e05b9474188ed082fb20031be.md)"
---

# Reactivity in Web Frameworks

In the context of a web framework, reactivity means that you can update your view when the application state changes.

```jsx
const app = document.getElementById('app')

app.innerHTML = `
	<button>-</button>
	<span>0</button>
	<button>+</button>
`;

const [decrementButton, incrementButton] = document.querySelectorAll('button');

const valueContainer = root.querySelector('span');

let count = 0;

decrementButton.addEventListener('click', () => {

count--;

valueContainer.innerText = count;

});

incrementButton.addEventListener('click', () => {

count++;

valueContainer.innerText = count;

});
```

The previous example is pretty bare bones and with the use of frameworks your code starts to focus more on application state updates while the framework takes charge of the reactivity part. To achieve the goal of updating a view, frameworks need to answer two questions: The "*WHEN*" and the "*WHAT*".

## **When does the application state change? AKA (The "WHEN")**

- Frameworks tends to have different approaches when it comes to determine when application state changed however all of them have their root in invoking a scheduleUpdate function the framework have in the source code.
- A common line of thought for scheduled updates of the application state is that they should probably be batched in some way since performing synchronous updates can lead to performance (see React Reactivity model for example).
- Batching scheduled updates also prevents renders from being out of sync and letting the users see strange UX states.

### **Mutation Tracking**

- The "*Mutation tracking*" consists in providing custom objects to users which they can treat as a normal POJO.
- The reason to use objects is because primitives cannot be mutated in JavaScript and we need to track how properties are changed. And because the use of objects is necessary for this, the this variable is then used to extract values from an hypothetical app.state in a this.appState manner.
- These "tracked" POJOs are created with functions provided by the framework (Let's say getTrackedObject(...)) where all of them are "hi-jacked" to allow custom behaviors inside their getters and setters.
- Mutation tracking can be performed with Proxies for ease of use, examples can be found in MobX, Vue.js and Ember.js.

```jsx
// Mutation tracking example implementation using proxy

function getTrackedObject(properties) {
  for (const propertyName in properties) {
    if (properties[propertyName] === 'object') {
      properties[propertyName] = getTrackedObject(properties[propertyName]);
    }
  }

  return new Proxy(properties, {
    set(target, key, value) {
      if (typeof value === 'object') {
        value = getTrackedObject(value);
      }

      target[key] = value;

      return value;
    },

    deleteProperty(target, key, value) {
      delete target[key];
    },
  });

  // Usage

  const appState = getTrackedObject({
    foo: 1,

    bar: [2, 3],
  });

  appState.foo = 3;

  appState.bar.push(4);

  appState.bar[0] = 'foo';
}
```

Once you are able to track application state changes, you need to invoke scheduleUpdate  to update the view accordingly.

### **Signaling**

- Another approach to determine when the application state changes is letting users signal the framework when an update is required.
- Signaling is about exposing the scheduleUpdate function to the framework user.
- This design leads to less complexity inside the framework but the complexity goes one layer above and is the user's responsibility to manage it.

```jsx
class Component {
  setAppState(appState) {
    this.appState = appState;

    scheduleUpdate();
  }
}

class MyComponent extends Component {
  someHandler() {
    // this will not schedule update

    this.appState.list.push('one');

    // you need to call setAppState after the .push()

    this.setAppState({ list: this.appState.list });

    // or instead, for a one-liner

    this.setAppState({ list: [...this.appState.list, 'one'] });
  }
}
```

### **Mutation tracking With Signaling**

- Instead of enforcing an setAppState function, frameworks can also provide custom event handlers where they believe application state can change.
- This is the Angular 1, reactivity model.
- This has the same complexity as the signaling model and can cause new developers some pain.

```jsx
function timeout(fn, delay) {
  setTimeout(() => {
    fn();

    scheduleUpdate();
  }, delay);
}

// User code

import { $timeout } from 'my-custom-framework';

class UIComponent extends Component {
  someHandler() {
    // will schedule update after the callback fires.

    $timeout(() => {
      this.appState.one = '1';
    }, 1000);

    setTimeout(() => {
      // this will not schedule update

      this.appState.two = '2';
    }, 1000);
  }
}
```

### **Static Analysis**

- The dilemma between mutation tracking and signaling is that:
    - We want to allow framework users to mutate application state freely that the mutation tracking.
    - We want to achieve mutation without runtime complexity that the signaling model provides.
- If we assume the problem is "Developer expressiveness vs runtime complexity" then we can make use of static analysis to achieve another middle ground solution.
- With the use of a compiler, we can attempt to modify the source code and insert scheduleUpdate whenever we believe that an application state change can occur.

```jsx
class UIComponent {

	someHandler() {
		this.appState.one = '1';
	}
}

// compiles to:

class UIComponent {
	someHandler() {
		this.appState.one = '1';
		scheduleUpdate(); // <-- insert this during compilation
	}
}
```

- This is the model that Svelte is built upon.
- Making the compiler smart enough to understand when updates should be apply is a highly difficult task. That is the exact reason Svelte limits the number of operators that can trigger reactivity such as +, =, ++, --, etc.

```jsx
class UIComponent {
  someHandler() {
    this.appState.one = '1'; // <-- ✅changes to application state

    this.foo = 'bar'; // <-- ⛔️ not changing application state

    const foo = this.appState;

    foo.one = '1'; // 🤷‍♂️ do we know that this is changing application state?

    doSomethingMutable(this.appState);

    function doSomethingMutable(foo) {
      foo.one = '1'; // 🤷‍♂️ do we know that this is changing application state?
    }

    this.appState.obj = {
      data: 1,

      increment() {
        this.data = this.data + 1; // 🤷‍♂️ do we know that this is changing application state?
      },
    };

    this.appState.obj.increment();

    this.appState.data.push('1'); // 🤷‍♂️ is push mutable?

    this.appState.list = {
      push(item) {
        console.log('nothing change');
      },
    };

    this.appState.list.push('1'); // 🤷‍♂️is this push mutable?
  }
}
```

## **When has the application state changed? AKA (The "WHAT")**

- Regardless of the method used to detect the application state has changed, what needs to happen afterward is the update of the view. The application needs to perform a certain strategy to let users see the updated application state without intermediate updates.
- Using the implemented method to track changes, we can obtain different amount of contextual information about what needs to be updated and form a spectrum using this information.

**The framework does not know about what has changed**

### **Rebuilding UI**

Given the framework does not know what needs to be updated, we can simply rebuild the UI given the new state.

- It has the cons that it may harm performance and also loses traits like: Cursor positioning, text highlighting, input focus, active state of elements, etc.

```jsx
function buildUi({ counter }) {
  const component = document.createElement('div');

  const decrementButton = document.createElement('button');

  decrementButton.textcontent = '-';

  component.append(decrementButton);

  const incrementButton = document.createElement('button');

  incrementButton.textcontent = '+';

  component.append(incrementButton);

  return component;
}

function update(root, applicationState) {
  root.innerHTML = '';

  const component = buildUi(applicationState);

  root.appendChild(component);
}
```

### **Fake DOM**

- To mitigate the cost of creating new elements constantly, a more well-thought technique appeared: Instead of tearing down and recreating every DOM element every-time, let's compare it against a previous representation and generate the list of actions that should be execute to make the view update.
- This is the approach React uses, the representation of the DOM is called "Virtual DOM".

```jsx
function buildUi({ counter }) {
  return {
    element: 'div',

    children: [
      {
        element: 'button',

        text: '-',
      },

      {
        element: 'span',

        text: counter,
      },

      {
        element: 'button',

        text: '+',
      },
    ],
  };
}

let previousUi = null;

function updateUi(root, applicationState) {
  const newUI = buildIntermediateUi(applicationState);

  const operationsNeeded = diff(newUi, previousUi);

  operationsNeeded.forEach(runOperation);

  previousUi = newUi;
}
```

### **The framework knows about what has changed**

- In this other side of the spectrum we have the framework who has already determined the exact operations that need to be performed at the moment the application state changes.
- The only thing the framework needs to do to update the view is apply such updates to the DOM.

```jsx
applyChanges(root, changes);

function update(root, changes) {}

function applyChanges(root, changes) {
  if ('counter' in changes) {
    root.querySelector('span').textContent = changes.counter;
  }
}
```

[Reactivity in Web Frameworks (Part 1)](https://tanhauhau.hashnode.dev/reactivity-in-web-frameworks-part-1-ck56y73lm03dmmus148vg617q)