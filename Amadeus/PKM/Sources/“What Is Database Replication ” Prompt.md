---
Notes: "What Is Database Replication?"
---

# “What Is Database Replication?” Prompt

> *Database replication is the process of copying data from a database on one server (the master) to one or more databases on other servers (the slaves). The goal of database replication is to have a backup of the data in case the original data is lost or becomes unavailable, as well as to distribute data across multiple servers so that it can be accessed by more users or applications.

There are several types of database replication, including:

Master-slave replication: In this type of replication, the master database receives all the updates and the slave databases receive a copy of the updates. The slave databases can only be read from, not written to.

Peer-to-peer replication: In this type of replication, all the databases in the system can be both read from and written to, and updates to any database are automatically replicated to all the other databases in the system.

Multi-master replication: In this type of replication, multiple databases can be updated independently, and the changes are replicated to all the other databases in the system.

Database replication is often used in situations where it is important to have a backup of data in case of a disaster, or where the data needs to be available to multiple users or applications in different locations. It is also useful for improving the performance of databases by distributing the load across multiple servers.*
>