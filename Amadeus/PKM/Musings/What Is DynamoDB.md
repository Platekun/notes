---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "DynamoDB"
status: "Processed"
sources: "Unknown"
---

# What Is DynamoDB?

The DynamoDB service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to create and configure [[Managed Databases|managed]]  key-value NoSQL databases.

DynamoDB’s business model revolves around being cost-effective while also providing low latencies, high scalability, high availability and high durability:  It uses SSD(s) to store data which is replicated redundantly across multiple availability zones (and even cross-region).

DynamoDB also has supports for:

- Global Tables: Database tables which are replicated across multiple regions, that is, highly available low latency tables.
- Streams: Used for time-ordered series of database item changes. It provides the ability to subscribe to these item changes.
- DAX: A database acceleration feature which implements a cache layer fully managed by AWS to speed up queries.

Since DynamoDB is a service for [[Managed Databases|managed]] databases, it performs all the heavy lifting that involves [[Self-Hosted Databases|self-hosting a database]] under the hood.