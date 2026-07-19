---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "RDS"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "October 25, 2022 1:38 AM"
sources: "Unknown"
---

# Databases Networking

When working with [[Amadeus/PKM/Musings/What Is RDS|RDS]] instances, a common setup for deployment would usually involve using two [[Subnetworks|subnets]], one [[Public Subnetwork|public]] and one [[Private Subnetwork|private]]:

- The [[Public Subnetwork|public]] one would be used to place resources like [[What is EC2|EC2]] instances. This is because web servers are supposed to be public from outside the [[What Is A VPC|VPC]]).
- The [[Private Subnetwork|private]] subnetwork would contain an [[Amadeus/PKM/Musings/What Is RDS|RDS]] instance. This is because database instances are only supposed to be available for nodes within the [[What Is A VPC|VPC]]. In case we needed something extra, we could use a NAT Gateway to obtain internet connectivity.