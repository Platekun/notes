---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Databases"
status: "Processed"
sources: "Distributed Database Management Systems Article, Distributed Database Definition"
---

# What Is A Dristributed Database?

A distributed database (commonly referred to DDBMS) is a database that stores data across a common network rather than at a centralized location.

Distributed databases are designed to have be [[Reliability|highly reliable]] (thanks to its distributed cluster of nodes and lack of central point of failure) and [[Availability|highly available]] (thanks to its high number of nodes). 

To keep their state in sync, they usually use a [[What Is Distributed Consensus|distributed consensus protocol]] such as [[What Is Database Replication|replication]] or [[What Is Database Duplication|duplication]], among others.