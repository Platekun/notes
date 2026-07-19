---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EventBridge"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 19, 2022 1:30 PM"
Sources: "EventBridge Definition"
---

# What Is EventBridge?

The EventBridge service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to [[Integration Services|integrate different applications]] by using [[Amadeus/PKM/Musings/What Is Serverless|serverless]] [[Amadeus/PKM/Musings/What Is An Event Bus|event buses]].

EventBridge’s business model revolves around its [[Amadeus/PKM/Musings/What Is An Event Bus|routing system]]: It listens for events (indicators of change) and applies a “*rule*” to understand which “*target*” should receive the event. “*Rules*” are responsible for matching events to “*targets*” based on their structure or a schedule.

EventBridge has support for multiple types of targets like [[Amadeus/PKM/Musings/What Is Lambda|Lambda]], [SQS](https://app.notion.com/p/25297c87c1664a07a37e30fb6078bfb0?pvs=21), [[What Is An HTTP API|HTTP]], email, SMS, mobile notifications, etc. Its catalog is wider catalog than [[Amadeus/PKM/Musings/What Is SNS|SNS]] and includes third-party integrations and has support cron-like actions.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> In order to set up our [[Amadeus/PKM/Musings/What Is An Event Bus|buses]] we have to use the [[How To Access AWS Using The AWS Management Console|management console]], however if we need to use them we have to use the EventBridge [[How To Access AWS Using AWS SDK(s)|SDK]] which allow us to interact them.

</aside>

![Untitled](What%20Is%20EventBridge/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/events/home?region=us-east-1#/)