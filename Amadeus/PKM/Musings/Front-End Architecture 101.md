---
Note Type: "Literature"
Author: "Nir Kaufman"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "Front-End Architecture 101: Nir Kaufman @ ReactNYC Talk"
---

# Front-End Architecture 101

## **Prologue**

Frameworks implements inversion of control, hence why React is more popular. Frameworks provide you a built-in architecture you should follow that's why when you choose React you should care about architecture because you don't get it from the start.

### **The Architect**

"*The first concern of the architect is to make sure the house is usable, It is not to ensure that the house is made out of bricks*" - Uncle Bob

There are two parts to an application: The essentials and the implementation details. In the case of a house the essentials are concerns like entries, space and restrooms while the implementation details are the building materials or the ornamentation.

![Untitled](Front-End%20Architecture%20101/Untitled.png)

The Entities (Data) and Use Cases are the essentials of an application while the implementation details are concerns like Presentation, Persistence and Technology.

The technology you chose in the end to create the implementation there are a set of decisions that are made for you, which includes other tools and patterns but it does not mean it fits your needs.

![Untitled](Front-End%20Architecture%20101/Untitled%201.png)

### Layers

Most of us don't know about architecture or we simply don't care about layers because it's not really touched upon in front-end education. Meanwhile it's a common concept in back-end development.

The idea of having a layer is slicing an application into a manageable unit of complexity.

In the image example the dependencies are all pointing down, which means the Presentation layer is depending on the application layer which is depending on the entities.

If you build a SPA implementing these ideas, it means the upper layer (React) does need the complexity of the other layers, it's decoupled.

![Untitled](Front-End%20Architecture%20101/Untitled%202.png)

When we talk about *entities* we are not talking about OOP (although the concepts come from OOP) but it can even be a functions, it does not really matter.

![Untitled](Front-End%20Architecture%20101/Untitled%203.png)

The application layer is about the use cases the application has and to fulfill those it makes use of the entities (We are only talking about user needs and not about tools).

![Untitled](Front-End%20Architecture%20101/Untitled%204.png)

The presentation layer is the one we usually care more about because of our education as front-end developers. We think in terms of UI components in this layer, something we can see and it's not abstract.

![Untitled](Front-End%20Architecture%20101/Untitled%205.png)

In our example there is a infrastructure layer, which also depends on the entities layer. The function of this layer is to provide persistence to the outer world and perform network calls but nothing concern with how entities behave.

![Untitled](Front-End%20Architecture%20101/Untitled%206.png)

The idea of having all these layers is being able to swap layers when needed, a deocupled architecture.

## **Architecture**

When thinking about design patterns there are old ones like the MVC and more modern ones like the Flux pattern defined by the React team, both of them are still relevant because we are always talking a basic concept:

- **"Loose Coupling, High Cohesion": The degree of direct knowledge that one element has of another.**
- Loose Coupling: When a developer tries being modular and applying encapsulation of the components.
- High Cohesion*:* When a developer attempts to keep similar and related things together.

![Untitled](Front-End%20Architecture%20101/Untitled%207.png)