---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Software Development"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 18, 2022 12:00 AM"
Sources: "Unknown"
---

# Understanding JavaScript Runtimes

## Execution Context

The execution context is an abstract compiler concept used to refer to the information of the environment of the code being executed. It is similar to a container which contains a:

- A memory component that stores all functions and variable. It is also known as the `variable environment`.
- A code component that executes code one line at a time. It is also known as the `thread of execution`.

There are two types of execution contexts:

- Global Execution Context: The execution context where all the code that is not inside a function gets executed.
- Function Execution Context: Everytime a function is invoked, the JavaScript runtime creates a new execution context inside the global execution context.

## Creation Phase

### Hoisting Step

During the hoisting step (Also known as global object setup step), the JavaScript runtime reads the code one line at a time. The purpose of this phase is to allocate memory to all the variable and functions declarations it recognizes.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Trying to access a variable before initialization is referred as the “*Temporal Dead Zone*”.

</aside>

- Variables are allocated in memory and initialized with the value of `undefined` .
    
    ```jsx
    console.log(x);
    
    // ReferenceError: Can't find variable: x
    ```
    
    ```jsx
    console.log(x);
    var x;
    
    // undefined
    ```
    
    ```jsx
    console.log(x);
    var x = 10;
    
    // undefined
    ```
    
- `const`, `let`  and `class` are allocated in memory but they are not initialized.
    
    ```jsx
    console.log(typeof name);
    // ReferenceError: Can't find variable: name
    
    let name = "John";
    ```
    
- Functions declarations are allocated in memory with the whole function body.
    
    ```jsx
    console.log(greet());
    
    function greet() {
    	console.info("Hello");
    }
    
    // Hello
    ```
    
- Functions expressions are treated the same way as variables:
    
    ```jsx
    console.info(greet());
    
    var greet = function() {
    	console.info("Hello");
    };
    
    // TypeError: greet is not a function. (In 'greet()', 'greet' is undefined)
    ```
    

### Scope Creation Step

In programming language theory, the scope is the “*region of a program*” where the set of name bindings of an execution context is valid. 

Scope prevent name collisions and determines the level of access of a piece of code from other parts of the codebase. This mechanism answers the questions: from where can a piece of code be accessed? From where can't it be accessed? What can access it, and what can't?

There are two types of scope:

- Global scope: Occurs when a variable is defined “*outside a function*”. These variables are made available to all of the functions within the source code.
- Local scope: Occurs when a variable is defined inside of a function.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> In the case of JavaScript the “*region of the program*” refers to an area of source code. This is why it is called “*lexical*” or “*static*” scope.

</aside>

```jsx
// Global scope.
var a = 1;

function greet() {
	// Local scope.
	var b = 2;

	// Can access `a` thanks to the lexical scope mechanism.
	console.info(a, b);
}

greet();
// 1, 2
```

Functions that make use of the lexical scope are called **closures:**

```jsx
function createGreet(greeter) {
	return greet(greeted) {
		// Can access the `greeter` variable through lexical scope.
		console.info(greeter + ": Hi " + greeted);
	}
}

createGreet("John")("Dan");
// "John: Hi Dan"
```

When resolving the name binding values, the JavaScript runtime will fall back to searching in outer scopes until it can find a value. This is what is referred to as **scope chain**.

### `this` Assignment Step

`this` is a JavaScript function used to refer to where an execution context belongs to however it has some particular behaviors:

- Global scope: `this` is set to the `window` object.
    
    ```jsx
    console.info(this);
    // Window
    ```
    
- Functions: `this` is set to the environment the function is created in:
    
    ```jsx
    var message = "Hey there"; 
    
    function greet() { 
    	console.log(this.message); 
    }
    
    greet();
    // Hey there
    ```
    
- Objects: `this` refers to the environment it is declared in
    
    ```jsx
    var message = "I will rule the world!"; 
    
    var Syndrome = {
    	message: "And when everyone is super, no one will be", 
    	monologue() {
    		console.log(this.message);
    	}, 
    }; 
    
    Syndrome.monologue();
    // And everyone when super, no one will be
    ```
    

## Execution Phase

During this phase, the JavaScript runtime reads and executes the code in the [[Understanding JavaScript Runtimes|global execution context]] one line at a time.

### Synchronous Behavior

JavaScript is a single-threaded programming language, this means that its runtimes has the following characteristics:

- They can only execute one instruction at a time.
- They use a data structure known as a [stack](https://en.wikipedia.org/wiki/Stack_(abstract_data_type)) to keep track of new execution contexts during the lifecycle of a script (Also known as “**Call Stack**”).
- They use a data structure known as a heap for dynamic memory management.

During [[Understanding JavaScript Runtimes|this phase]], if the current instruction happens to be a function invocation, a new [[Understanding JavaScript Runtimes|function execution context]] is created. The new execution will have its own [[Understanding JavaScript Runtimes|Creation Phase]].

![](https://thecodest.co/images/uploaded/2020/03/asynchronous-and-single-threaded-javascript-meet-the-event-loop/stack.gif)

Once a function invocation context is completed, the runtime removes it from the stack and resumes with the next instruction of the current execution context.

It can happen that some functions invokations can have high execution times, if this occurs the runtime will appear unresponsive, this is referred as “*blocking the main thread*”.

![Reading a large file can be considered as a blocking synchronous operation.](https://thecodest.co/images/uploaded/2020/03/asynchronous-and-single-threaded-javascript-meet-the-event-loop/blocking.gif)

Reading a large file can be considered as a blocking synchronous operation.

### Asynchronous Behavior

JavaScript can also behave as it if were a multi-threaded programming language, meaning it can execute instructions concurrently without blocking the current execution context. This happens because JavaScript runtimes are built using multi-threaded programming languages like [C++](https://es.wikipedia.org/wiki/C%2B%2B) or [Rust](https://www.rust-lang.org). Runtime developers expose these async APIs to us (web developers). Examples of these APIs are `setTimeout` or `fetch`.

The asynchronous behavior of JavaScript is based on an “*event loop*”, responsible for executing the code, events management and tasks execution.

During [[Understanding JavaScript Runtimes|this phase]], if the current instruction happens to be a function invocation which involves using an API provided by the runtime, the function passed will be sent to the runtime API's queue where it will wait for some amount of time to be invoked.

![](https://thecodest.co/images/uploaded/2020/03/asynchronous-and-single-threaded-javascript-meet-the-event-loop/callback-queue.gif)

While this happens, the runtime proceeds with the next instructions of the script. 

After the runtime executes its API, it will send the input function to a message queue where it will wait until the call stack becomes available.

At some point during the event loop, the runtime starts handling the messages of the queue starting from the oldest. When this occurs the message is removed from the queue and the input function is invoked, creating a new [[Understanding JavaScript Runtimes|execution context]] which is added to the [[Understanding JavaScript Runtimes|call stack]].

## Read More

[Execution Context in Javascript](https://anuradha.hashnode.dev/execution-context-in-javascript)

[Programming Fundamentals](https://press.rebus.community/programmingfundamentals/chapter/scope/)

[JavaScript Execution Context - How JS Works Behind The Scenes](https://www.freecodecamp.org/news/execution-context-how-javascript-works-behind-the-scenes/)

[Asynchronous and Single-threaded JavaScript? Meet the Event Loop](https://thecodest.co/blog/asynchronous-and-single-threaded-javascript-meet-the-event-loop)

[Thread (computing) - Wikipedia](https://en.wikipedia.org/wiki/Thread_(computing)#Single-threaded_vs_multithreaded_programs)