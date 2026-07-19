---
Note Type: "Literature"
Author: "Enrico Polanski"
Primary Zettelkasten Area: "Routing"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Routing Concerns Should Be Isolated"
---

# Separation Of Concerns In A Router

*Routing*, *navigation* and *state* should be kept separate since complexity can grow uncontrollably.

Routers should map to views.

**Application state is independent of views.**

> *Library creators keep overcomplicating routing and navigation and state by mixing all of them together. A router should match a route with a view. Not a route with the state of the application and the view state. Those cannot be mapped together in any non trivial use case. A router should map a path with a view, it is not its job to also handle the specific state and transitions. /foo is /foo independently from my previous scrolling position, the fact I'm logged or not, etc. A router has to map /foo with the corresponding view(s), nothing else.*
> 

[https://twitter.com/EnricoPolanski/status/1258727101982703616?s=20](https://twitter.com/EnricoPolanski/status/1258727101982703616?s=20)