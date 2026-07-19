# What Can We Cache Using Application Caching?

Area: Systems Design (https://app.notion.com/p/Systems-Design-a6bc2656ba664b749fca2279aa67a6fc?pvs=21)
Reveal: No
Confidence: Confident
Answer: We can cache two categories of data:
- Objects: Treat runtime objects the same way as cache. This means it’s normal to store runtime objects inside the cache.
- Database queries: Cache results from the database queries we perform.
Last edited time: January 16, 2023 12:13 AM