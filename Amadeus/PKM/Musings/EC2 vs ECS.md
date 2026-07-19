---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ECS"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "EC2"
Status: "Processed"
Created time: "November 3, 2022 12:35 AM"
Sources: "What Is The Difference Between Amazon ECS And ECS?"
---

# EC2 vs ECS

[[Amadeus/PKM/Musings/What Is AWS|AWS]] recommends using [[Amadeus/PKM/Musings/What Is ECS|ECS]] if we are running containers in the cloud. The reason for not doing so using [[What is EC2|EC2]] instances is because while it is possible to run our containers it also comes with a big responsibility. Here are some of the tasks we need to take into account:

- Installing [Docker](https://app.notion.com/p/cbb66315176749bbb8a001ecc9a043bd?pvs=21).
- Keeping [Docker](https://app.notion.com/p/cbb66315176749bbb8a001ecc9a043bd?pvs=21) updated.
- Creating our images.
- Running our containers.
- Distributing our containers across multiple [[What is EC2|EC2]] instances.
- Connecting the different instances and containers.
- Perform logging and analytics.

[ECS](https://app.notion.com/p/8e8f195c08e944629791523bc987e804?pvs=21) takes care of the heavy lifting that involves achieving high availability, scaling, logging, etc. while we focus on our project.