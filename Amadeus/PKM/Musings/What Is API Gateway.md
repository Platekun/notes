---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "API Gateway"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 9, 2022 1:09 AM"
Sources: "Unknown"
---

# What Is API Gateway?

The API Gateway service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to create [[Amadeus/PKM/Musings/What Is Serverless|serverless]] [[What Is An HTTP API|HTTP APIs]]. It has support for [[Amadeus/PKM/Musings/What Is A REST API|REST APIs]] and Websocket APIs.

In order to use API Gateway we have to provide the [[What Is An HTTP API|API]] structure: The resources, paths and [[What Is HTTP|HTTP]] methods, query parameters, authentication and response status codes and schemas. Besides the structure we must also provide the code to be executed which must reside within [[Amadeus/PKM/Musings/What Is Lambda|Lambda]].

It also has more advanced features like rules for handling requests, response creation and forwarding logic.

Since API Gateway is a service for managed [[What Is An HTTP API|APIs]], it performs all the heavy lifting that involves handling and scaling the [[What Is An HTTP API|API]] under the hood.

![Untitled](What%20Is%20API%20Gateway/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/apigateway/main/apis?region=us-east-1)