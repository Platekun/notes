---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "App Sync"
status: "Processed"
sources: "Unknown"
---

# What Is AppSync?

The AppSync service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to create [[Amadeus/PKM/Musings/What Is Serverless|serverless]] GraphQL and PubSub [[What Is An HTTP API]]APIs.

In order to use API Gateway we have to provide the [[What Is An HTTP API|API]] structure: The schemas, queries and mutations, resolvers, data sources and authentication. Besides the structure we must also provide the data sources ([[Amadeus/PKM/Musings/What Is DynamoDB|DynamoDB]], [[Amadeus/PKM/Musings/What Is Aurora|Aurora]], [[Amadeus/PKM/Musings/What Is Lambda|Lambda]], etc.).

It also has more advanced features like rules for handling requests on real time and caching.

Since AppSync is a service for managed [[What Is An HTTP API|APIs]], it performs all the heavy lifting that involves handling and scaling the [[What Is An HTTP API|API]] under the hood.

![Untitled](What%20Is%20AppSync/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/appsync/home?region=us-east-1#/)