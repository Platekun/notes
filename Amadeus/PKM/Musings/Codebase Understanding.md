---
Note Type: "Permanent"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Developer Mindset"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 2:50 AM"
---

# Codebase Understanding

Being placed in a codebase is a problem you will encounter regardless your seniority status, both juniors and seniors face this problem every-time they change jobs.

When you first sit down at that project and being ask to implement different features, you don't really know where everything is and that's the main difference between knowing the syntax of a language and knowing a language.

Don't take anything your boss tell you like they are being purists because nobody in practice follows everything perfectly. Even if he/she answers the questions for "*What architecture are you using?*", "*What tools are you using?*", "*We do FP*", etc. Their definitions of that practice have their own flavor of that thing, that's something all people do in society, take the bits they care or understand and make their own definitions. That's the reason why just explaining some things won't immediately make you productive.

Before jumping into code, It is advised to know and understand the business model, ideally there should be some documentation or diagrams over the services we have on the system ("Ideally" because that is not always the case for all the projects). There should be a person or a few people at the very least that have the combined knowledge of the entire system but you need to figure who these people are and as quickly as you can. This is where your soft skills are helpful because if you can get connected to these people and create relationships with these them, you can easily get an introduction to this part of the system.

- **Your goal as a new programmer is to fit-in, learn the practices first. You have to be able to answer the question "What's the expected way to build a new feature?".**

## **Helpful Tips**

- Have a "*don't get stuck rule*": You should always try to solves issues on your own but as soon as you get stuck for more than 15-20 minutes or so you should ask your mentor for help. If you get stuck you can figure most things out in 15 minutes, it's most likely you will need hours to get unstuck. **It's advised to use an actual timer to track your progress**.
- Ask your mentor / buddy / boss / coworker to give you a high level overview of the system or part of the system: Philosophy, architecture, style, third-party tools, etc.
- Ask for history lessons about some certain pieces of code came to be, and about the decisions taken.
- Use Code Review: This is the way to go if you want to obtain knowledge from your coworkers. You can learn more about the codebase and how to introduce changes more holistically.

## **Helpful Questions**

- “*What's the main feature or the thing that does best*" (AKA The selling point of the project)?
- How do you run or test the project?
- What specific tooling knowledge do you need? (Frameworks, libraries, etc.).
- “*Do I need to configure something in my environment*?"
- What differences are between the different environments of the project (Development, QA, Staging, Production, etc.)?

## **Approaching a UI + API project**

It's really useful to think of the application as a big tree of features where each feature is coupled to an URL (with some search parameters). Once you understand the selling point of the application you can look at that page and check for the network requests.

- Take a look at the network tab and ask yourself "*Which endpoint did I hit?*" and "*Where did I call that endpoint*?"
- Look at the and with the URLs and now you have the **entry points of your system**.
- Start looking the place where those endpoints live and navigate all your way down to database or external services calls. Doing so will get you to know your way around the codebase and looking what patterns have been applied.

**Always start looking at the route level and sort your way to the deep bottom of your system. Every program has an entry point that goes until a database call. The worst thing you can do it's looking at random files without any real purpose.**