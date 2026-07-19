---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ASG"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 11, 2022 2:16 AM"
Sources: "Unknown"
---

# What Is An Auto Scaling Group?

Auto scaling is an [[What is EC2|EC2]] feature offered by [[Amadeus/PKM/Musings/What Is AWS|AWS]] that allow us to [[Horizontal Scalability|add or remote instances]] [[Elasticity|based on certain criteria]] in order to handle our workloads. 

This feature is based on the idea creating an “*Auto scaling group*” which is a group of instances associated with a desired, minimum and maximum [[Horizontal Scalability|capacity]] plus a set of rules, called “[[Scaling Policies|*scaling policies*]]”.

The size of an auto scaling group will depend on the number of instances desired:

- It will scale out to match the increased load.
- It will scale in to match the decreased load.

![Untitled](What%20Is%20An%20Auto%20Scaling%20Group/Untitled.png)

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> [[Amadeus/PKM/Musings/What Is IAM|IAM]] [[Roles]] used with auto scaling groups will be inherited by the [[What is EC2|instances]].

</aside>