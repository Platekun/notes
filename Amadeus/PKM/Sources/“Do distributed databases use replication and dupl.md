---
Notes: "What Is Database Duplication?, What Is Database Replication?"
---

# “Do distributed databases use replication and duplication?” Prompt

> *Distributed databases are databases that are spread across multiple servers or locations, and are designed to allow multiple users or applications to access and modify the data stored in the database simultaneously.

Distributed databases often use replication to ensure that the data is available and consistent across all the servers or locations. Replication involves copying data from a database on one server (the master) to one or more databases on other servers (the slaves). The goal of replication is to have a backup of the data in case the original data is lost or becomes unavailable, as well as to distribute data across multiple servers so that it can be accessed by more users or applications.

In a distributed database, replication is often used to ensure that all the servers in the system have the same data, and to allow users to access the data from any server in the system. This can improve the performance and availability of the database by distributing the load across multiple servers.

Distributed databases may also use duplication to create a backup of the data in case the original data is lost or becomes unavailable. However, duplication is typically not used to distribute data across multiple servers or locations in a distributed database, as this is the role of replication. Instead, duplication is used as an additional backup or disaster recovery measure in case the primary data is lost or becomes unavailable.*
>