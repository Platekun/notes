---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 27, 2022 2:09 AM"
Sources: "What You Should Know About Database Caching, Systems Design Primer"
---

# Write Behind Caching Strategy

In this cache strategy the application is responsible for writing to the cache, while the cache is responsible for writing the data to the database in an asynchronous manner (e.g. every 2 minutes).

![Untitled](Write%20Behind%20Caching%20Strategy/Untitled.png)

### Pros

- Best case scenario involves 1 write operation.
- Cache will be always fresh (in theory).
- Lower latency compared to [[Write-through Caching Strategy|write-through]].

### Cons

- Cache nodes do not have data until written. This happens when scaling or restoring from failures.
- Not resilient to cache node failures. There can be data loss.
- High complexity.