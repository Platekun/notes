---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 27, 2022 12:56 AM"
Sources: "What You Should Know About Database Caching, Systems Design Primer"
---

# Cache-Aside Caching Strategy

In this cache strategy (also known as “*lazy-loading*”) the application is responsible for reading and writing from the database. Cache and database are independent from each other.

When a query needs to be executed:

Look for a cache entry in cache.

1. Result present: Return the result.
2. Result not present: Load entry from the database.
    1. Write the result to the cache.
    2. Return the result.

![Cache hit.](Cache-Aside%20Caching%20Strategy/Untitled.png)

Cache hit.

![Cache miss.](Cache-Aside%20Caching%20Strategy/Untitled%201.png)

Cache miss.

```jsx
async function getBooksByAuthorId(cache, db, authorId) {
	const key = `SELECT * FROM books WHERE authorId = ${authorId}`;

	let result;

	try {
		result = await cache.get(key);

		if(result !== null) {
			return result;
		}

		return db.query("SELECT * FROM books WHERE authorId = {0}", authorId);
	} catch (error) {
		throw new QueryError("getBooksByAuthorId");
	}
}
```

## Pros

- Base case scenario involves 1 read operation.
- Resilient to database failures.
- Resilient to cache node failures.

## Cons

- Worst case scenario involves 2 read and 1 write operation. This happens when a key is looked up for the first time or has been removed (TTL).
- Data can be stale and show inconsistencies between cache and database, this is why it is recommended to use with a time-to-live (TTL).
- High latency if a cache node fails, response time is affected.