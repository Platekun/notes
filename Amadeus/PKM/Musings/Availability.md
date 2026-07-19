---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Systems Design"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 6, 2022 2:19 AM"
Sources: "Unknown"
---

# Availability

Availability is the ability of a system to be available at any given point of time. Availability is often mentioned when speaking about downtimes.

In [[Amadeus/PKM/Musings/What Is AWS|AWS]] context, highly available systems are systems that were [[Horizontal Scalability|horizontally scaled]] through multiple [[Availability Zones|availability zones]] in order tu survive a possible data center loss.

Availability in cloud-base system is higher because we can leverage the cloud provider’s network (In [[Amadeus/PKM/Musings/What Is AWS|AWS]]’ case it’s called Global Reach) to make our application highly available to more customers over the world.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Obtaining highly available systems is the reason [[Amadeus/PKM/Musings/What Is AWS|AWS]] recommends (enforces) using resources on different [[Availability Zones|availability zones]].

</aside>