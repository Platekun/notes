---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EC2"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 11, 2022 11:50 PM"
Sources: "Unknown"
---

# What is EC2?

The Elastic Compute Cloud (also known as EC2) service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to rent “*virtual*” computers.

A “*virtual*” computer  is a slice of a physical computer that AWS owns (in their data centers).  Each “*slice*” of the physical machine is completely isolated from the other “*slices*”, with their own dedicated hardware.

These “*slices*” are commonly known as “*instances*”.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> EC2 instances are fully configurable: We can choose their OS, CPU, RAM, Storage space, Network card and Firewall rules.

</aside>

![Untitled](What%20is%20EC2/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/ec2/v2/home?region=us-east-1)