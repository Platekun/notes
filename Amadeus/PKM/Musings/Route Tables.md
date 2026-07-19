---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "VPC"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "September 30, 2022 2:13 AM"
Sources: "Unknown"
---

# Route Tables

A route table contains a set of rules, called “*routes*”. It specifies how packets are forwarded between [[Subnetworks|subnets]] within a [[What Is A VPC|VPC]], the internet and the [[What Is A VPC|VPC]] connection.

Within a [[What Is A VPC|VPC]], route tables are assigned to individual [[Subnetworks|subnets]] (hence the usage of [[What Is CIDR|CIDR]] ranges). We can have different types of setups like: Having a single route table for the entire [[What Is A VPC|VPC]], 1 table route per subnet, etc.

A route table looks like this:

| Destination | Target | Status |
| --- | --- | --- |
| `10.0.0.0/16` | local | **Active** |
| `172.31.0.0/16` | [[What Is A Subnet|`<<SubnetId>>`]] | **Active** |
| `0.0.0.0/0` | [[Internet Gateway|`<<InternetGatewayId>>`]] | **Active** |

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> [[Subnetworks|Subnets]] that are associated to a route table that redirects all traffic to an [[Internet Gateway|internet gateway]] are called [[Public Subnetwork|public]].

</aside>

[AWS Routing 101](https://medium.com/@mda590/aws-routing-101-67879d23014d)