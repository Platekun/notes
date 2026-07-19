# What Is Cache-aside About?

Area: Systems Design (https://app.notion.com/p/Systems-Design-a6bc2656ba664b749fca2279aa67a6fc?pvs=21)
Reveal: No
Confidence: Confident
Answer: The cache-aside caching strategy is one of the most common caching techniques:
Everytime we perform a query we attempt to check if it’s present in the cache, if not we retrieve the results and store them in the cache. If it’s present then we simply return the cached value.
Last edited time: January 15, 2023 11:15 PM