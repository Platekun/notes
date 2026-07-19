---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "VPC"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 5, 2022 2:47 AM"
Sources: "Unknown"
---

# What Is A VPC?

A Virtual Private Cloud (also known as VPC) is a concept created by AWS used to refer to to our own network in the cloud.

The idea is that we can have multiple resources which can be grouped into one or more VPCs. Using VPCs allow us to logically isolate those resources from other networks in the cloud and control their network settings like:

- [[IP Addresses|IP addresses]] assignment.
- Network traffic.
- Internet connectivity.

VPCs can span through multiple [[Regions|availability zones]]. 

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> All AWS resources must reside within a VPC.

</aside>

![Untitled](What%20Is%20A%20VPC/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/vpc/home?region=us-east-1)