---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Databases"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Distributed Programming"
Status: "Processed"
Created time: "December 30, 2022 1:52 AM"
Sources: "Consensus Definition, How Does Consensus-Based Replication Work in Distributed Databases?, Cob: a leaderless protocol for parallel Byzantine agreement in incomplete networks"
---

# What Is Distributed Consensus?

Consensus is a problem present in distributed programming where a system needs to achieve an agreement regarding a computation. Systems that need to solve consensus make use of a consensus “*protocol*”, a specialized algorithm and rules, in order to reach one.

Consensus protocols can be broadly classified in:

- **Leader-based**: Protocols that define a "*leader*” database which is responsible for the data updates. This allows for highly consistent systems.
- **Leaderless**: Protocols that require several nodes of the system to share their proposal for the computed value. This allows for systems with high availability due to the lack of a “*leader*” node, however it is accompanied with an increase in implementation complexity.

The problem of consensus can be seen in multiple contexts like [[What Is Cloud Computing|cloud computing]], [[What Is A Dristributed Database|distributed databases]], among many others.