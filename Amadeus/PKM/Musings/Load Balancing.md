---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Systems Design"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 7, 2022 1:11 AM"
Sources: "Unknown"
---

# Load Balancing

Load balancing is a technique used to distribute a set of requested operations (also referred more ambiguously as traffic) across a set of machines (called nodes). The idea is to utilize all the available resources equally.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> “*Requested operations*” usually mean things like database read / write requests.

</aside>

The actor in charge of performing load balancer is called a “*load balancer*” which can be hardware or software based.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Load balancers can be thought as reverse [proxies](https://app.notion.com/p/476888f99b3d4f0bba80c3797ee6e719?pvs=21).

</aside>

## Advantages

- Allows systems to scale [[Horizontal Scalability|horizontally]].
- Allows systems to be [[Elasticity|elastic]].
- Allows systems to be [[Availability|highly available]].
- Serve as a single point of access (Infrastructure abstraction): End users only know about the load balancer and not the different nodes of the system.
- Allows for deployments with minimal downtime.
- Provides [[SSL And TSL|SSL/TSL]] to websites.

## Health Checks

Load balancers are also responsible for running [[Health Checks|health checks]] on instances to determine whether or not it is healthy. If an instance is healthy it means it’s available for traffic.

![Untitled](Load%20Balancing/Untitled.png)

## Read More

[System Design - Load Balancing](https://medium.com/must-know-computer-science/system-design-load-balancing-1c2e7675fc27)

[Load balancing: system design interview concepts (4 of 9)](https://igotanoffer.com/blogs/tech/load-balancing-system-design-interview)

[Load Balancer - System Design Interview Question - GeeksforGeeks](https://www.geeksforgeeks.org/load-balancer-system-design-interview-question/)