---
Note Type: "Literature"
Author: "Garran Means"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "Web UI Architecture"
---

# Web UI Architecture

![Untitled](Web%20UI%20Architecture/Untitled.png)

## What is “Architecture”?

When we think about architecture we often answer with "***The decisions you make about your application***", a phrase that involves:

- File organization and folder structure.
- Design patterns (models, views, etc.).
- State and/or messaging.
- Routing concerns.
- Development processes like testing and minifying.

## Top Level Characteristics

A few of the characteristics of an architecture that matches well with our domain problem are:

- It provides the ability to write minimal boilerplate code.
- It provides a curated library of tools.
- It show us the obvious ways of accessing anything.
- It displays clear implementation and style patterns.
- It balances performance and maintenance concerns.

## Architecture Responsibilities

The architecture we strive for should fulfill some responsibilities to us and to the project:

- Provide necessary libraries and utilities as needed.
- Create a single page application needing only concepts and not by using scaffolding.
- Verify its own health. It should known when it's broken.
- Provides an optimized version of itself (Different environments optimizations).

## When Do We Spend Time Designing Our Architecture?

We cannot simply stop development and spend months architecting requirements. Architecture time is spread in different situations which results in an architecture evolving through time.

It is important to mention that shape and patterns of an architecture are not always clearly visible, this usually happens because the application complexity is still not big enough to need such a rigid architecture (Objects are not collections, application states are handled mostly by CSS, no back-end objects needed to be observed from the user interface).

Some of the *“architecture time*” moments are we face something like the following:

- A page has multiple, well defined-types of objects.
- Messaging needs to go beyond interaction events.
- A given page contains multiple states.
- There is repeated code for in order to connect other parts of the code.
- We have several developers working on the same single page application.
- Testing involves recreating complex workflows.

There can be many more situations however they are all similar in regards that we need to make architectural changes like:

- Cataloguing Objects: What kind of concrete type of objects do we have and how do they relate to each other?.
- Diagraming States: The same ones we would define in a state chart.
- Planning: What interactions and requirements we will have.

## Good Architecture’s Starter Pack

- **Code Sketching**
    - Think about object inheritance.
    - Consider what can be sync and what is async.
    - Try to reveal the abstractions you will need.
    - Your abstractions can be used to build or choose a framework.
- **Messaging Responsibilities**
    - Notify events subscribers.
    - Cache subscribers
    - Track context of events (metadata associated).
    - Forward data (Send useful event payloads).
    - Allows decoupling from async code.
- **Rendering**
    - Provide rendered HTML.
    - Interpolate data.
    - Register partials.
    - Cache compiled templates.
- **Server Interaction**
    - Pass server data to requesting object.
    - Pass client data to server.
    - Branch correctly on errors.
    - Decoupling of URLs from instance code.
    - Notify application when data is sent or received (Using event sourcing or any other means of communication).
- **State Management Responsibilities**
    - Allow objects to have one ore more states.
    - Fire off correct chain of events when the state changes.
    - Modify current properties of objects when the state changes.
    - Do you use routes with state management? Not really because a URL is something you navigate to while state is more of a building block for routing.
- **Validation**
    - Is not a part of the framework.
    - It's a part of the application logic.
    - Display validation results to user.
    - Update state information when things are invalid.
    - Abstract common validation functions.

## Common JavaScript Application Architectures

- MVC: Model View Controller ([https://en.wikipedia.org/wiki/Model–view–controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)).
- MVVM: Model View ViewModel ([https://en.wikipedia.org/wiki/Model–view–viewmodel](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)).
- MVP: Model View Presenter ([https://en.wikipedia.org/wiki/Model–view–presenter](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter)).
- PAC: Presentation - Abstraction - Control ([https://en.wikipedia.org/wiki/Presentation–abstraction–control](https://en.wikipedia.org/wiki/Presentation%E2%80%93abstraction%E2%80%93control)).
- Event Driven Architecture ([https://en.wikipedia.org/wiki/Event-driven_architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)).

**The pattern chosen only matters a little but it's not the success factor of an architecture**.