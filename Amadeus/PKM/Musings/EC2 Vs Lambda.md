---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Lambda"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 2, 2022 9:37 PM"
Sources: "AWS Lambda Vs EC2: Which To Use And When"
---

# EC2 Vs Lambda

## EC2

- We are charged per second of use time.
- It has to be integrated with other services such as [[What Is An Auto Scaling Group|ASG]] and [[Amadeus/PKM/Musings/What Is ELB|ELB]] to scale.
- Pricing can be lower once a sufficient amount of traffic is met.
- Works best when used for building websites and application servers.
- No latency when waiting for requests to be processed.

## **Lambda**

- We are charged per second of run time.
- [[Amadeus/PKM/Musings/What Is AWS|AWS]] takes care of scaling and availability.
- Pricing can be lower at the beggining of a project.
- Works best when used for data manipulation in a consistent basis.
- Suffers from latency when function has not been invoked in a while (Cold start).

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The comparison only takes into account the use case of building websites and APIs however EC2 is more versatile.

</aside>