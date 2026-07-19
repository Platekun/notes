---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Systems Design"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 18, 2022 12:15 AM"
Sources: "Difference Between Bus And Queue, Message Queues, Message Queue Definition"
---

# What Is A Message Queue?

A message queue is message-passing technique where a queue is used for communication between two “*processes*”.

Messages put into the queue are stored for a period of time until the recipients retrieves them. Queues work in a first-in-first-out (FIFO) manner. Each message is processed only once, by a single consumer.

## Pros

- Decoupling: Publishers do not know where the message is being used and consumers do not know about producers.
- Scalability and Elasticity: Publishers and consumers can be scaled independently.
- High reliability: because messages are only processed once and in the right order.

## Cons

- It is not a broadcast mechanism. When a consumer processes the message, it is no longer available for other consumers.
- There is complexity in creating, configuring and monitoring the message queues.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The term “*processes*” can be swap with “*interfaces*”, “*modules*”, “*applications*”, “*programs*” or “*system nodes*”

</aside>

![Untitled](What%20Is%20A%20Message%20Queue/Untitled.png)