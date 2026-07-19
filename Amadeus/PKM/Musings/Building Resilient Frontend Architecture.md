---
Note Type: "Literature"
Author: "Monica Lent"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "GOTO 2019 - Building Resilient Frontend Architecture"
---

# Building Resilient Frontend Architecture

![Untitled](Building%20Resilient%20Frontend%20Architecture/Untitled.png)

## Why Do We Usually Rewrite Code?

- Inexperience.
- It's fun.
- Better solution available
- Technical debt: Code that negatively and repeatedly affects the speed or quality of delivery.

## **Recurring Technical debt**

Usually there is a point where devs cannot take it anymore and propose or impose a refactor to fix this problem but after doing that big refactor the situation where adding features is dreadful comes again.

Legacy code often differs from the suggested alternative because it's actually working and scaling.

## **Cost of software development**

The real cost of software development is not the initial development but maintenance over time which is why the question should be "*How can we make our systems resilient to this inevitable change?*"

The solution to the question above is "*Good Architecture*" but that word has become a dirty word because your average software developer does not know what it means to have a good architecture. “*What does a software architect even do*?” It feels detached from daily problems and sounds too elite.

Why don't we think about architecture as "*enabling constraints*"? Constraints about how we use data and code that help us move faster over time.

## **Enabling Constraints In Programming Paradigms**

- Paradigm: Constraint & Enablement.
- OOP: From function pointers to classes → Independently deployable subcomponents.
- FP: From immutable data → Eliminate race conditions and concurrency problems.
- var → const: No more reassignment → Predictable data.
- jQuery → React: No more DOM manipulation → Predictable UI.
- CSS → CSS-in-JS: No more naming / side-effects → Safety and fewer global names.

We are constraining ourselves all the time and we do it on purpose because we trade constraints for safety and speed.

There is a lot of discussion about directory structure but not about what part of the application depends on other parts.

- Big Ball of Mud: If you don't have any rules on what depends on what you probably has a big ball of mud with dependencies pointing in any direction.
- Layered: This is the case when you have some rules about what should depend on what, and should only point in a single direction.
- Modular: Creating new JavaScript Modules does not make the code modular. This is more a monorepo / micro-front-end approach.

### Why should you care?

Think about what happens when you introduce a change in a big-ball-of-mud architecture, even with all the promises you do to your QA engineer there's the probability to introduce more regressions which can even cause cross-team conflicts because somebody somewhere changed something and did not realize they broke something else.

Now if you think about introducing a change in the layered approach, we know there will be regressions but such regressions will be controlled in a secluded area of the application.

When source code dependencies point inward it's easier to isolate the impact of changes.

What about shared components? If you can take out the business logic you can stick it in the design system or maybe you are better off copy and pasting rather than introducing more dependencies into the system.

Too much DRY can cause brittle and side-effect ridden code in the name of code reuse.

Decoupled > DRY: Code reuse is not a goal in and of itself. The purpose of code reuse is to avoid introducing bugs unnecessarily. **Avoid coupling code that diverges over time.**

Whenever someone creates a new feature they are not checking the documentation so how can you enforce those constraints?

Forbidden dependency tests: Tests that force the app to break in any parts that should not depend on the code try to depend on it (Look up dependency-cruiser)

## **Preserve your architecture over time or Enforce your boundaries.**

![Untitled](Building%20Resilient%20Frontend%20Architecture/Untitled%201.png)

Every time you write a function (or don't), create a new module (or don't), you are making an architecture decision.