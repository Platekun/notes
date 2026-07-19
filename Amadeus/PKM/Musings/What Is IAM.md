---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "IAM"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 11, 2022 1:00 AM"
Sources: "Unknown"
---

# What Is IAM?

The Identity And Access Management (also known as IAM) service is a global service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to manage our identity and access concerns. It relies on two big concepts: identites and access management.

**Identities**

- Entities that can *do* something in our account.
- Identities answer the question “*Who is allowed to do something?*”.
- Example of identities are users, user groups and roles.

**Access Management**

- We can control the permissions that are granted to an identity.
- Access management answers the question “*What is an entity allowed to do?*”.
- Example of access management are permissions (managed via policies.)

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The account we create the first time we sign up to [[Amadeus/PKM/Musings/What Is AWS|AWS]] is our “*Root account*”, which should never be shared or used.

</aside>

![Untitled](What%20Is%20IAM/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/iamv2/home?region=us-east-1#/home)