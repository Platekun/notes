---
Area: "RDS"
Reveal: "No"
Confidence: "Confident"
Answer: "RDS provides two endpoints we can use to connect to the Aurora nodes."
---

# What Mechanisms Does Aurora Provides For Connections At Code Level?

- A writer endpoint which will talk to the primary instance. This is used for write operations.
- A reader endpoint which will talk to a load balancer which forwards the traffic to a read replica. This is used for read operations.
Last edited time: January 15, 2023 11:18 PM