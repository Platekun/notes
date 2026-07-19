---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Databases"
last-edited-time: "September 20, 2023 2:23 AM"
secondary-zettelkasten-area: "Distributed Programming, Systems Design"
status: "Processed"
created-time: "December 30, 2022 2:33 AM"
sources: "Database Replication Definition, “What Is Database Replication?” Prompt, “How is it different from database duplication?” Prompt, “Do distributed databases use replication and duplication?” Prompt, \"Is database replication considered an horizontal scaling techique?” Prompt, \"Can replication and duplication be considered consensus protocols in distributed databases?” Prompt"
---

# What Is Database Replication?

Replication is an [[Horizontal Scalability|horizontal scaling]] technique and [[What Is Distributed Consensus|distributed consensus protocol]] that consist in copying data from a database in multiple copies of it (called [[Read Replicas|read replicas]]). The goal of database replication is to have a backup in case the original data is lost or is not available.