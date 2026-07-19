---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EventBridge"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 18, 2022 12:58 AM"
Sources: "Enterprise Service Bus Definition, AWS Certified Cloud Practitioner (CLF-C01) | AWS Essentials (../Sources/AWS%20Certified%20Cloud%20Practitioner%20(CLF-C01)%20AWS%20Ess%20bbbd66f0293243b3b198a4fa0b7894c7.md), Event-based Microservices: Message Bus, Event-based Microservices: Overview"
---

# What Is An Event Bus?

An event bus (also known as message bus) is a software architecture component used to perform communication between different “*processes*” (popular with microservices systems).

Event buses use the [[What Is PubSub|publish/subscribe]] technique which allows consumers to subscribe to messages of certain type and then connect the producers and consumers all-together. 

When working with microservices there is no direct line of communication between each service. Instead, systems make use of the event bus’ “*event routing*” to accomplish this: The event bus takes in “*output events*” and provides them to any microservice which take those events as “*inputs events*”.  With event routing the responsibility of subscribing to data falls on the service requesting it.

The messages processed by the event bus are not guaranteed to be in FIFO manner however they can be persisted and provided to any service which connects to the event bus.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The term “*processes*” can be swap with “*interfaces*”, “*modules*”, “*applications*”, “*programs*” or “*system nodes*”

</aside>

![Untitled](What%20Is%20An%20Event%20Bus/Untitled.png)