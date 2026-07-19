---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Fargate"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "November 3, 2022 2:22 AM"
sources: "Unknown"
---

# What Is Fargate?

Fargate is a [[Amadeus/PKM/Musings/What Is Serverless|serverless]] execution environment created by [[Amadeus/PKM/Musings/What Is Lambda|AWS]]. As a [[Amadeus/PKM/Musings/What Is Serverless|serverless]] technology, this means we don’t have to worry about choosing the right EC2 instance or any hardware profile.

To use Fargate we need to provide a simplified set of hardware settings (similar to [[Amadeus/PKM/Musings/What Is Lambda|Lambda]]) which is used by [[Amadeus/PKM/Musings/What Is ECS|ECS]] to provide provide us with the needed infrastructure.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Serverless is a convoluted term here because it really means “*managed*”. Fargate pricing shows that the billing is similar to [[What is EC2|EC2]], the biggest appeal is not owning the EC2 instances it replaces.

</aside>