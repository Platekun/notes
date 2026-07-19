---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "SQS"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "November 19, 2022 11:44 AM"
sources: "Unknown"
---

# What Is SQS?

The Simple Queue (Also known as SQS) service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to [[Integration Services|integrate different applications]] by using [[Amadeus/PKM/Musings/What Is Serverless|serverless]] [[What Is A Message Queue|message queues]].

While we lose control of our infrastructure we still have some configuration settings like: queue order (standard or FIFO), message settings (timeouts, retention period, delivery delay, size and polling time), encryption and access policies.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> In order to set up our [[What Is A Message Queue|queues]] we have to use the [[How To Access AWS Using The AWS Management Console|management console]], however if we need to use them we have to use the SQS [[How To Access AWS Using AWS SDK(s)|SDK]] which allow us to interact them.

</aside>

![Untitled](What%20Is%20SQS/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/sqs/v2/home?region=us-east-1#/homepage)