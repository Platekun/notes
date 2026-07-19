---
note-type: "Literature"
author: "Heliton Nordt"
primary-zettelkasten-area: "Software Architecture"
last-edited-time: "September 20, 2023 2:23 AM"
secondary-zettelkasten-area: "React"
status: "Processed"
created-time: "October 18, 2022 12:58 AM"
sources: "Modeling Apps As A Machine Which Spawns Actors"
---

# Eliminating Business Logic From The View Using Actors

State Charts let us decouple business logic from our user interface. This way components could just subscribe to them and send events.

> *With [#XState](https://twitter.com/hashtag/XState?src=hashtag_click) Actors you can model your entire app using a single machine. This machine might spawn other machines.
Your view layer doesn't need to know anything about the business logic, it just subscribes to state changes and send events.*
> 

[https://twitter.com/hnordt/status/1154549791071887360](https://twitter.com/hnordt/status/1154549791071887360)