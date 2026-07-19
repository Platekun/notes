---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "RDS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 25, 2022 12:53 AM"
Sources: "Unknown"
---

# What Is Multi AZ?

The multi availability zone deployment (also known as “*Multi AZ*”) is a deployment setup for [[Amadeus/PKM/Musings/What Is AWS|AWS]] [[Amadeus/PKM/Musings/What Is RDS|databases]]. It consists of having a primary database instance that updates a standby replica synchronously located in a different availability zone.

When a disaster occurs that involves not being able to communicate with the primary instance database, the [[Stand By Replicas|standby replica]] will swap places and become the primary instance instead.