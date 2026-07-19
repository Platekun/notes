---
Note Type: "Literature"
Author: "Paulus Esterhazy"
Primary Zettelkasten Area: "Routing"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "App Routing Insights"
---

# URL (s) and Routing Logic Correctness

An thin abstraction is needed to handle the complexity that is using routing logic everywhere. As a consequence this could also make the URL(s) structure logic trivial or at least simpler. 

If one could think of routers are controllers then it would make sense not to mix view logic with controller logic.
Single Page Application lifecycle management is a very important concern that is not addressed properly. Part of this lifecycle management falls to the router which some people believe it should be in responsible of fetching the data needed for the place about to be rendered. This could explain API (s) like `beforeModel` from Ember.

If we accept the fact that a router should be data-driven, then it should be limited to:

- Parse locations into states to invoke the correct data transition functions (for data fetching).
- Construct URL(s) from states.

When a transition occurs, the navigation event is usually created by the user which means it is just like using a button’s click handler.

Following from [‣](https://app.notion.com/p/f0aaaca3b4a84753bdb369062023804b?pvs=21), [‣](https://app.notion.com/p/9e4557a04eab489b96fe4838ecacc364?pvs=21) and [‣](https://app.notion.com/p/3bf8df7444354d158eb3ae86d6388c97?pvs=21). We can observe that a router’s role is obscured due to all the complexity we have in the web environment. A router can be simple if we take the time to understand the distinct concepts.

> *Because of the complexity of browser behavior (history, server-side vs client-side, etc) many don't understand how routing works under the hood. There's nothing magical about it, but it's important to take the time to learn the concepts (not just how library XYZ works).*
> 

> *Getting the routing logic and URL structure right is a crucial part of writing an SPA. Many people underestimate this and end up with convoluted code as a result

The router is part of the C of MVC, not the V. Router libraries should know nothing about view libraries like React. Router5 (which has an optional React plugin) gets this right.*

Contrary to popular belief, the router is often the right place for data loading and resource lifecycle management in SPAs. Embrace the fact that route activation is an asynchronous process that can involve network I/O

*A good router lib is data-driven and bidirectional. Based on a definition, it should parse location.pathname into a data structure and call (asynchronous) route transition functions with that data. It should also construct paths from data. That's all it should do.

Navigation events are almost always user-initiated. Treat them like click handlers. The initial location.pathname also represents a user action.

Programmatic navigation actions can include "hidden" parameters that aren't visible as part of the URL. Ask yourself, should the UI state be the same if you reload?*
> 

[https://twitter.com/pesterhazy/status/1258647300337020928?s=20](https://twitter.com/pesterhazy/status/1258647300337020928?s=20)

[https://twitter.com/pesterhazy/status/1258647408424243200?s=20](https://twitter.com/pesterhazy/status/1258647408424243200?s=20)

[https://twitter.com/pesterhazy/status/1258647520043032577?s=20](https://twitter.com/pesterhazy/status/1258647520043032577?s=20)

[https://twitter.com/pesterhazy/status/1258647705196417024?s=20](https://twitter.com/pesterhazy/status/1258647705196417024?s=20)

[https://twitter.com/pesterhazy/status/1258647851342725121?s=20](https://twitter.com/pesterhazy/status/1258647851342725121?s=20)

[https://twitter.com/pesterhazy/status/1258648197997658112?s=20](https://twitter.com/pesterhazy/status/1258648197997658112?s=20)

[https://twitter.com/pesterhazy/status/1258648370257805312?s=20](https://twitter.com/pesterhazy/status/1258648370257805312?s=20)