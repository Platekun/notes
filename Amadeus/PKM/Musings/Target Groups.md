---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ELB"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 10, 2022 11:42 PM"
Sources: "Unknown"
---

# Target Groups

To perform load balancing, [[Amadeus/PKM/Musings/What Is AWS|AWS]] introduces the concept of a “*target group*”. Target groups tells the load balancers where the traffic should be forwarded to (be it [[What is EC2|EC2]] instances,  [[IP Addresses|IP address]], or other kind of resources). We can use one or multiple target groups depending on our architecture.

The load balancer will monitor the [[Health Checks|health]] of all the resources inside a target group.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Targets that are forwarded traffic cannot read the [[IP Addresses|IP address]] of the original client, however they are stored in a `X-forwarded-For` header.

</aside>

![Untitled](Target%20Groups/Untitled.png)