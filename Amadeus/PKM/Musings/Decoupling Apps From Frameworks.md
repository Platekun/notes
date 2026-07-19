---
Note Type: "Literature"
Author: "Robert Aguilera"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "Frontend architecture: Decoupling apps from frameworks (DevFest 2019)"
---

# Decoupling Apps From Frameworks

![Untitled](Decoupling%20Apps%20From%20Frameworks/Untitled.png)

## **Problems Architectures Addresses**

- Repeated boilerplate code.
- Changes ripple through the system.
- Duplicated almost similar logic.

## **Principles about Software Architecture**

Software architecture is not about folders & files, it's just a tiny piece of it. What you are looking for is the connection between these components.

### **Volatility**

Think about the data format and how that data format ripples throughout your system. "*What's the liability to change rapidly and unpredictably?*" Think about the scope of those changes.

If our application is a lake and you throw a rock at it, how does the water ripples behave in your system? Which parts are going to be affected? That's called volatility.

### Types **of Logic**

When we are working in react we are thinking about coupling some lifecycle hook to an external API call and then rendering on the screen but what's happening it's that there are different kind of logic here, a Front-End logic and a Back-End-ish logic.

In software architecture we think of that as the presentation layer (All the stuff that interacts with the UI) and a specification layer (All the things we have to do to make the UI do its job).

The end user does not really care about the differentiation between this logic, they just want to use the product to fulfill their needs which is what we do in Front-End, we couple all these things into a together. What software architecture tries to make us think in terms of modules: High level modules and lower level modules.

- High Level Modules: Consumed by the presentation layer.
- Low Level Modules: Help the high level modules do their work.

Not all logic is the same. We separate this different kind of logics using abstractions (The act of representing essential features without including the background details or explanations).

`return paymentProcessor.processCreditCard(payload).`

The study about software architecture it's about patterns that you use to build systems that are:

- Easy to reason about.
- Can easily shrink and scale.
- Easy to change.

To write useful and long term maintainable software we tend to look out for patterns and group them into abstractions.

### **Inversion of Dependencies**

Depend on abstractions rather than concretions.

Higher level modules should depend on abstractions that use the lower level modules and not in the lower level modules with all the details.

It uses abstraction to protect from pain due to the volatile parts of your system.

Implementation does not matter to higher level modules, which makes it easier to think about your code: "*Just provide your abstraction*".

There will be always a level of coupling because we have to know the name of things and methods, but we think of that as communication.

## **Benefits Of A Well-suited Architecture**

- It provides a stable presentation layer.
- We can make Isolated changes.
- Expanding or contracting modules is easy.
- It is easier to understand connections between modules.
- We can focus on what my system does instead of what my specific presentation needs.