---
Note Type: "Literature"
Author: "Heliton Nordt"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "React"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Modeling Apps As A Machine Which Spawns Actors"
---

# Eliminating Business Logic From The View Using Actors

State Charts let us decouple business logic from our user interface. This way components could just subscribe to them and send events.

> *With [#XState](https://twitter.com/hashtag/XState?src=hashtag_click) Actors you can model your entire app using a single machine. This machine might spawn other machines.
Your view layer doesn't need to know anything about the business logic, it just subscribes to state changes and send events.*
> 

[https://twitter.com/hnordt/status/1154549791071887360](https://twitter.com/hnordt/status/1154549791071887360)