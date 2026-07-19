---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 19, 2022 2:10 PM"
Sources: "What Is Pub/Sub? Publish/Subscribe Messaging Explained, Publish-Subscribe Pattern"
---

# What Is PubSub?

The Publish-subscribe (also known as PubSub) pattern is message-passing where a notification system is used for communication between “*processes*”.

“*Publishers*” will publish messages to a “*topic*” and the “topic” will push the message to all the “*subscribers*”.

## Pros

- Decoupling: Publishers do not know where the message is being used and subscribers do not know about producers.
- Development simplicity: Allows for multiple runtimes and brokers.
- Allows for real-time communication.
- Scalability and Elasticity: Publishers and subscribers can be scaled independently.

## Cons

- Unnecesary complexity for small projects.
- Debugging complexity: Hard to diagnostic system-wide bugs.
- Not suitable as a streaming solution.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The term “*processes*” can be swap with “*interfaces*”, “*modules*”, “*applications*”, “*programs*” or “*system nodes*”

</aside>

![Untitled](What%20Is%20PubSub/Untitled.png)