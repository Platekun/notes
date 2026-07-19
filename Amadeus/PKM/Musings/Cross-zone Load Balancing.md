---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ELB"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 6, 2022 2:23 AM"
Sources: "Unknown"
---

# Cross-zone Load Balancing

Cross-zone load balancing is a featured offered by [[Amadeus/PKM/Musings/What Is AWS|AWS]] that allows us to distribute the load across all [[Availability Zones|availability zones]] where we have a [[Amadeus/PKM/Musings/What Is ELB|load balancer]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> This is enabled by default in [[Application Load Balancer|application load balancers]] (cannot be disabled). It can also be enabled in [[Network Load Balancer|network load balancers]].

</aside>

![Not using cross-zone balancing would mean the load balancer with two resources could become overloaded because there are less resources to handle requests.](Cross-zone%20Load%20Balancing/Untitled.png)

Not using cross-zone balancing would mean the load balancer with two resources could become overloaded because there are less resources to handle requests.