---
Note Type: "Literature"
Author: "Yehuda Katz"
Primary Zettelkasten Area: "React"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Ember"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Components Are Not The Primary Unit Of Composition In Front-End Apps"
---

# React References And DOM Behavior

React hooks are considered a big step in the right direction in composition and ergonomic terms, but there are problems left like letting consumers decide how to work with element references. This problem is a consequence of the popular trend of thinking that components exists as a way to facilitate coupling data to DOM.

Another look can give us an unpopular view: Maybe components in front-end frameworks exists as a way to facilitate data flow and coupling data to DOM is mostly a special case that should be used sparingly. A proof of this statement is that multiple frameworks provide a “*directives*” API just like in Angular, Sue and Ember.

We can dream if React could provide an API for abstracting DOM behavior (Like the lifecycle of elements) in a way that works with any element just like ember modifiers do in Ember.

> *Heterodox view: components are not the primary unit of composition in front end apps.
Components facilitate data flow. Coupling data flow to DOM as a matter of course creates DOM abstractions that are hard to reuse.

Frameworks know this, which is why every framework has a few privileged "directives" (like event handlers) that work with any element and don't use the component abstraction.

Some frameworks provide a nice way to create your own directives (Vue is a good example), but even those frameworks claim that you should think of custom directives as an advanced feature, and that components are the primary form of reuse.

One of the consequences of this is that component APIs frequently have a privileged "main element" concept, and you get more tools for working with that main element (including lifecycle facilities) than other elements. There's no real reason for this.

I don't think Ember Octane really got to the end of this story, but Octane components don't even have a notion of a "main component", let alone a privileged one. You use our version of "directives" (which we call modifiers) to abstract over DOM lifecycle; they work on any element

React Hooks are heading in the right direction here, but the API for abstracting over DOM stuff requires creating a ref and then sticking it on an appropriate element and juggling lifecycle.

Think of Ember modifiers as a dedicated ref syntax that you can stick on any element. The modifier is created (with the element) when the element is created, and its teardown is invoked when the element is invoked.
You don't create or manage refs.

The modifier's syntax is on the element, so that's how it gets associated with the element.
Here's the Ember equivalent of a React on-resize hook.

`<div {{did-resize this. onResize}}>
    Resize the window to see the modifier in action
</div>`*

`import Component from '@ember/component';
import { action } from '@ember-decorators/object';`

`export default class ResizableComponent Extends Component {
    @action onresize(element: HTMLElement) {
        console.log('div resized!')
    }
 }`

*Don't focus on the separate template file. We agree it's not ideal and will eventually allow those two files to be one file, perhaps even in the next edition.
Also don't focus on the exact details of where the curlies are located. It takes some getting used to for sure.

The point is that you can very easily abstract away the onResize logic into a modifier, and that once you've done so, the entire API is "stick it on an element".
For reference, here's a pretty good version of a hook API for the same thing.*

`import React from "react";
import useResizeObserver from "use-resize-observer";

const App = () => {
    const { ref, width = 1, height = 1 } = useResizeObserver<HTMLDivElement>();

    return <div ref={ref}>Size: {width}x{height}</div>;
};`

*I think the general philosophy of hooks is heading in the right direction here, but the extra juggling that you have to do to attach the ref (compared to invoking a component) can get cumbersome, especially in larger components.

This may make it seem like writing general-purpose DOM abstractions separate from data flow is begging for extra boilerplate, and might make a person familiar with hooks think that it's worth it if you're writing a library, but not necessarily a good rule of thumb.

Another point worth making about ref w/ hooks: because of the way refs get attached, they don't naturally function as lifecycle managers for DOM elements.

This means that abstractions using useRef are relying on the state eventually settling after render happens enough times and useCallback/useEffect stops running.
This is really not ideal, because it creates tons of nonsense intermediate states.

Again, I think react is heading in the right direction here, but ultimately I believe that we should all be iterating on idiomatic ways to attach lifecycle to arbitrary elements that are *so nice* that we can stop thinking of components as the primary way to abstract DOM behavior

I know Ember's currently approach isn't ideal, but with Octane components, we put our money where our mouth is and completely eliminated the notion of a root element, as well as Component APIs that interact with the DOM.

You abstract DOM behavior in modifiers, and modifiers work on any element, in any component. Event handlers are just built-in modifiers, and the old component lifecycle behavior was recast into a modifier that works on any element.

Writing a modifier is pretty ergonomic. Function-based modifiers look a lot like React Hooks, and even support the "returning a function" cleanup API.

This means that you can mix and match modifiers built with any high-level modifier implementation on stable Ember, including experimental approaches, and they all boil down to the same stable primitive. This has been incredible for our own iteration.

Finally, for those not familiar with the Ember ecosystem, Octane is not an experimental approach I'm optimistic about. Octane landed in December 2019, and most apps are writing new code using Octane idioms.
So despite the imperfect API, this approach has worked out well.

I'm excited to keep iterating on these ideas, but I gotta tell you: I don't miss the pre-Octane DOM APIs on Ember's components one bit.
Moving element abstractions away from component invocations was difficult to think through at the time, but boy was it worth it.*
> 

[https://twitter.com/wycats/status/1352852581991636994](https://twitter.com/wycats/status/1352852581991636994)

[https://twitter.com/wycats/status/1352852582977261570?s=20](https://twitter.com/wycats/status/1352852582977261570?s=20)

[https://twitter.com/wycats/status/1352852591303041025?s=20](https://twitter.com/wycats/status/1352852591303041025?s=20)

[https://twitter.com/wycats/status/1352852592729104384?s=20](https://twitter.com/wycats/status/1352852592729104384?s=20)

[https://twitter.com/wycats/status/1352852593593073664?s=20](https://twitter.com/wycats/status/1352852593593073664?s=20)

[https://twitter.com/wycats/status/1352852594486464512?s=20](https://twitter.com/wycats/status/1352852594486464512?s=20)

[https://twitter.com/wycats/status/1352852595363090432?s=20](https://twitter.com/wycats/status/1352852595363090432?s=20)

[https://twitter.com/wycats/status/1352852601826463746?s=20](https://twitter.com/wycats/status/1352852601826463746?s=20)

[https://twitter.com/wycats/status/1352852603126779905?s=20](https://twitter.com/wycats/status/1352852603126779905?s=20)

[https://twitter.com/wycats/status/1352852609447514112?s=20](https://twitter.com/wycats/status/1352852609447514112?s=20)

[https://twitter.com/wycats/status/1352852610970128384?s=20](https://twitter.com/wycats/status/1352852610970128384?s=20)

[https://twitter.com/wycats/status/1352852611804798976?s=20](https://twitter.com/wycats/status/1352852611804798976?s=20)

[https://twitter.com/wycats/status/1352852618435915776?s=20](https://twitter.com/wycats/status/1352852618435915776?s=20)

[https://twitter.com/wycats/status/1352852620012974080?s=20](https://twitter.com/wycats/status/1352852620012974080?s=20)

[https://twitter.com/wycats/status/1352852620969340929?s=20](https://twitter.com/wycats/status/1352852620969340929?s=20)

[https://twitter.com/wycats/status/1352852621812396034?s=20](https://twitter.com/wycats/status/1352852621812396034?s=20)

[https://twitter.com/wycats/status/1352852622726709248?s=20](https://twitter.com/wycats/status/1352852622726709248?s=20)

[https://twitter.com/wycats/status/1352852634659557376?s=20](https://twitter.com/wycats/status/1352852634659557376?s=20)

[https://twitter.com/wycats/status/1352852636421120000?s=20](https://twitter.com/wycats/status/1352852636421120000?s=20)

[https://twitter.com/wycats/status/1352852637562015745?s=20](https://twitter.com/wycats/status/1352852637562015745?s=20)

[https://twitter.com/wycats/status/1352852638648332288?s=20](https://twitter.com/wycats/status/1352852638648332288?s=20)

[https://twitter.com/wycats/status/1352852639776612352?s=20](https://twitter.com/wycats/status/1352852639776612352?s=20)