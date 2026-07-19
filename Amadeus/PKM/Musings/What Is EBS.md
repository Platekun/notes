---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EBS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 12, 2022 10:10 PM"
Sources: "Unknown"
---

# What Is EBS?

The Elastic Block Store (also known as EBS) service is a service provided by [[What is EC2|AWS]] used to create “*virtual*” hard drives that can be attached to [[What is EC2|EC2]] instances. These volumes persist information outside of the [[What is EC2|EC2]] instance lifecycle.

As the “[[Elasticity|*elastic*]]” part of the name implies, volumes can be scaled dynamically as needed.

An EBS volume works as a [[Network Drive|network drive]] under the hood, meaning the [[What is EC2|EC2]] instances communicates with it using a network.

EBS volumes can be mounted and unmounted from an [[What is EC2|EC2]] instance to another [[What is EC2|EC2]] instance, however this is limited to an [[Availability Zones|availability zone]].

![Untitled](What%20Is%20EBS/Untitled.png)

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> There is complete freedom regarding how the volume’s contents are structured.

</aside>