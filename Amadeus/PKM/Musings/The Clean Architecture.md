---
Note Type: "Literature"
Author: "Ian Cooper"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "DevTernity 2019: Ian Cooper - The Clean Architecture"
---

# The Clean Architecture

![Untitled](The%20Clean%20Architecture/Untitled.png)

Uncle bob has repeated previously that the ideas exposed in the "*Clean Architecture*" book are not new and that those ideas come from others architectures:

- The hexagonal architecture from Alistair Cockburn
- The onion architecture from Jeffrey Palermo
- Boundary, Entities and Controllers from Ivar Jacobson.

All these architecture have common properties and Robert Marting synthesized those ideas in Clean Architecture.

## **Layering**

Is one of the most architectural styles there is and one of the first people created. The idea is to view your software as a wedding cake and outer layers should use inner layers.

The most common standard is having three layers: UI, Domain and Infrastructure.

- The UI is the one used by the user to interact with the system.
- The Infrastructure is in charge of speaking with external systems.
- The domain is the core of your application.

These layers are exposed to one upper layers using a thin facade as a public API (depending on your programming language).

A key rule of layering is that upper layers depend on bottom layers but not viceversa.

- **Note: You can have any amount of layers you need to represent your system and this standard is just a convention.**

## **Benefits**

One of the goals of architecture is reasoning about your system in an easier way. With layering we can reason about a layer as a coherent whole, without worrying about the implementation of others layers.

The second benefit is that you can substitute layers with alternative implementations. Change is quite constant in a system that lives the test of time and having this option is really valuable.

The third benefit is that you can defer decisions about layer implementations.

The fourth benefit is that we can reduce dependencies between layers because we are programming against a thin facade:

- Coupling: The property that one module is forced to change because another does.
- Cohesion: The property that a module is subject to the same forces of change.

Layers reduce coupling and increase cohesion.

## **Business Logic**

We can distinguish two types of "*business logic*".

- Domain Logic: Has to do purely with the domain, such as calculating an insurance premium, or figuring out the shortest path to ship a package. "*What are the rules we are encoding in our system?*"
- Application Logic: Has to do with the application responsibilities, often referred to as workflow logic.

Due to the different nature of these business rules, it's often seen that the domain layer is split in 2: A Entities layer and a Service layer. To accomplish this separating there are two approaches:

- **Domain Facade Approach**: Have a service layer implemented as a set of thin facades over a domain model, exhibiting the defining characteristics of the service layer.
- The classes implementing the facades don't implement any business logic, the domain model implements all the business logic.
- The facades establish a boundary and a set of operations through which client layers interact with the application.
- Operation Script Approach: Have a set of thicker classes that directly implement application logic domain. This is used more when dealing with mostly CRUD operations.
- Operations available to the clients are implemented as scripts, organized several to a class defining a subject area of related logic.
- **You can have parts of your system with one approach or another.**

## **Ports and Adapters**

A "*ports & adapter*" architectural style (Hexagonal Architecture) is a variation of the layered architectural style which makes clear the separation between the:

- Application: Layer containing the rules of our application (Not the whole application but the core / heart of the business).
- Adapters: The layer that deals with the outside world. The layer abstracts the inputs to the application and our outputs.
- Ports: An intermediary layer between the application and the adapters. They are used for purposeful conversations between the actor and the domain model.

Thinking about terms in this way, we can think about the conventional layer in these terms:

- The UI and the Infrastructure layer will belong to the adapters layer, performing IO operations.
- The application layer is equivalent to the domain layer.
- Anything in between is the ports.

The big question is "*How do I save something If I cannot depend on outer layers?*". In order for an inner layer to depend on an outer layer we have to use the principle of dependency inversion and provide an interface to perform such operation.

- **The idea of using dependency inversion is supporting layered architectures. We want to get rid of any adapters concern in the application layer. The application layer should be pure objects that are easy to use with TDD.**

**Boundary, Entities and Controllers**

Ivar Jacboson is famous for his book "*Object-Oriented Software Engineering*", his book is remembered for its usage of use case diagrams.

Ivar Jacbson was a driver behind use case diagrams. They are used to answer the question "*What are the set of interactions that make this software requirement*"? without drowning into details. They are used to represent flow of how a user given an input receives an outcome.

"*I want my software to be capable of showing you its dealing with use cases, I don't want my software to focus on the frameworks used to build it. When I look at my software I don't want to be drawn into thinking 'Oh, this is an MVC application' or 'Oh, this is a Ruby on Rails application', what I want to be drawn to is the use cases of my software and how it implements them.*".

- Boundary: An object that interfaces with actors, i.e, user interfaces, gateways, proxies, etc.
- Entity: Entities are objects representing systems data
- Controller/Interactor: Mediators between boundaries and entities. They **orchestrate**the execution of commands coming from the boundary.

This way of thinking is very similar to the hexagonal architecture: The adapters are boundary objects, the ports are interactor objects and the application represent the entities.

One of the other things Ivar Jacobson mention is that the interactor objects are the ones in charge of implementing our use cases. There should be an interactor for every use case. It executes the use case by talking to entities and boundaries. All the interactors together contain specific business logic or rules.

***Note**: An old idea of TDD is testing your use cases.*

## **Convergence**

Alistair Cockburn also wrote a book about writing use cases and then went up to present the hexagonal architecture. He explains:

A port is the "*use case boundary*" and use cases become problematic when they become focused on technology concerns. Use cases written against the ports can elide those concerns and focus on the application rules, making them easier to write and maintain.

Let's try to think "*What are the use cases and what are the business requirements?*".

There is a correlation between the "*use case boundary*" and the "*test boundary*": Tests should focus on the behaviors expressed by a use case, not on a unit of code

*Your focus is intended to be in the use cases and not testing the framework.*