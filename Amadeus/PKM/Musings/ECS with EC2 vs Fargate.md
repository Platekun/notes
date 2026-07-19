---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Fargate"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 4, 2022 12:55 AM"
Sources: "ECS With EC2 Vs Fargate, Moving From EC2 To ECS Fargate, Any Ggotchas We Should Be Aware Of?"
---

# ECS with EC2 vs Fargate

## ECS + EC2

- More complex as we have to think about scaling with our clusters.
- Well suited when we have spare [[What is EC2|EC2]] instance capacity.
- Well suited if we desire entire control of the cluster.
- Can cost less however we have the responsibility of mantaining our cluster of [[What is EC2|EC2]] instances.
- Billed for compute time including idle time.

## Fargate

- Simpler setup as scaling and monitoring is done for us.
- Well suited when we don’t want to spend time on setup and mantainance or as an alternative to tasks that surpass [[Amadeus/PKM/Musings/What Is Lambda|Lambda’s]] allowed execution time.
- Fargate is much more limited in terms of features than [[What is EC2|EC2]].
- Can cost higher when used with long-running tasks.
- Billed for the amount of vCPU, memory and storage our containers use including idle time