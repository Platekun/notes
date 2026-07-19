---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "IAM"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 11, 2022 12:49 AM"
Sources: "Unknown"
---

# AWS Security Model

The [[Amadeus/PKM/Musings/What Is AWS|AWS]] security model is called the “*shared responsibility model”.*  The idea is that “*security*” is a shared responsibility between both parties, [[Amadeus/PKM/Musings/What Is AWS|AWS]] and us. Each party is responsible for securing the things under their control.

**AWS**

- [[Amadeus/PKM/Musings/What Is AWS|AWS]] is responsible for the security of their infrastructure and physical machines.
- [[Amadeus/PKM/Musings/What Is AWS|AWS]] protects the internal systems and procceses to avoid malicious actors.
- [[Amadeus/PKM/Musings/What Is AWS|AWS]] is responsible for securing managed services and anything we cannot control.

 **Us**

- We are responsible are for how secure the code that makes up our applications is.
- We have to protect our account and control the account access.
- We are responsible for everything we are able to control and configure.