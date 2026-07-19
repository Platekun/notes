---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "RDS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 25, 2022 12:21 AM"
Sources: "Unknown"
---

# Aurora Connection Management

We need two endpoints in order to work with Aurora:

## Writer Endpoint

This endpoint is used to perform write operations and manipulation statements. It connects to the primary database.

## Reader endpoint

This endpoint is used to perform read operations. It connects to a load balancer which sends the request to a read replica.

![Untitled](Aurora%20Connection%20Management/Untitled.png)