---
Note Type: "Literature"
Author: "Kent C. Dodds"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Front-End Development, Distributed Programming, Caching"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Application State Is Client-Side Cache Of Server State"
---

# Server State

In distributed programming we cannot simply have a single source of truth stored in the client, data usually lives in another  computer and clients have to request and cache it for some amount of time. This becomes hard when it’s time to determine which data is stale and which one is fresh. It’s usually the server who can better guess when the data is stale. ReactQuery, SWR and similar libraries are trying to bridge the gap in this by allowing developers to invalidate response data (queries) when they need.

> *Lots of what we call "Application State" is actually just a client-side cache of server state. And just with any cache, invalidation is a hard problem.
Interestingly, I don't think many apps really consider this, but it's pretty important. 

For example, when a user updates some data, most apps I've seen (and built) will make a request to make the update, and when it's successful, they update the state (client-side cache) as well. Sometimes the order is switched in optimistic UIs.

In either case, how do you know that the rest of the data you have in your cache is still current? Maybe another user changed data in another entity (or even a different property of the same entity).

In your app, if the application state on the server got updated, how long would it take for the client to have those changes reflected in the UI? 

This is why I'm increasingly interested in simpler libraries like react-query which simply invalidate entire queries and rerequest everything on mutations (and even when the user refocuses the app) rather than libraries like Apollo which try to stitch together state changes.

It's all trade-offs (consistency/correctness vs resource management). But I think more apps could be made simpler and provide a better user experience by favoring correctness.*
> 

[https://twitter.com/kentcdodds/status/1228727040238473216](https://twitter.com/kentcdodds/status/1228727040238473216)

[https://twitter.com/kentcdodds/status/1228727041324793857?s=20](https://twitter.com/kentcdodds/status/1228727041324793857?s=20)

[https://twitter.com/kentcdodds/status/1228727042440458240?s=20](https://twitter.com/kentcdodds/status/1228727042440458240?s=20)

[https://twitter.com/kentcdodds/status/1228727045049348096?s=20](https://twitter.com/kentcdodds/status/1228727045049348096?s=20)

[https://twitter.com/kentcdodds/status/1228727046198587393?s=20](https://twitter.com/kentcdodds/status/1228727046198587393?s=20)

[https://twitter.com/kentcdodds/status/1228727047846891520?s=20](https://twitter.com/kentcdodds/status/1228727047846891520?s=20)