---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "RDS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 24, 2022 11:16 PM"
Sources: "Unknown"
---

# What Is Aurora?

Aurora is Amazon’s own propietary relational database engine which is compatible with MySQL and PostgreSQL. It has opinionated defaults from Amazon which result into higher performance that the other offered database engines however it also results into higher costs.

- It has supports up to 15 read-replicas.
- It can update up to 6 read replices simultaneously.
- Almost instantaneous failovers.

## Higher Availability For Data

Aurora’s [[Read Replicas|read replicas]] are stored redundantly in multiple availability zones which makes our data durable and [[What Is Availability|highly available]].

## Higher Availability For Database Instance

If the primary database instance happens to fail for some reason, Aurora can convert one of the [[Read Replicas|read replicas]] into a primary instance.