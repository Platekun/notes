---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "RDS"
status: "Processed"
sources: "Unknown"
---

# What Is Multi AZ?

The multi availability zone deployment (also known as “*Multi AZ*”) is a deployment setup for [[Amadeus/PKM/Musings/What Is AWS|AWS]] [[Amadeus/PKM/Musings/What Is RDS|databases]]. It consists of having a primary database instance that updates a standby replica synchronously located in a different availability zone.

When a disaster occurs that involves not being able to communicate with the primary instance database, the [[Stand By Replicas|standby replica]] will swap places and become the primary instance instead.