---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Systems Design"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "RDS"
Status: "Processed"
Created time: "October 24, 2022 11:38 PM"
Sources: "Unknown"
---

# Read Replicas

A read replica is a special type of database instance that serves as a copy of the primary database instance. As the name implies, they only support read-only operations and are used mechanism to offload requests from the primary instance (e.g, analytics traffic) or as a backup in case the primary instance fails for some reason.

When a write operation is performed on the primary database instance, read replicas are then updated asynchronously with the event data.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Read replicas are a way to obtain higher availability but in order to accomplish that, they must live in different locations which can result into varying costs depending on the cloud provider.

</aside>

![Untitled](Read%20Replicas/Untitled.png)