---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 27, 2022 2:31 AM"
Sources: "Things You Should Know About Database Caching"
---

# Read-through Caching Strategy

In this cache strategy the application is responsible for reading to the cache, while the cache is responsible for retrieving the data from the database.

![Cache hit.](Read-through%20Caching%20Strategy/Untitled.png)

Cache hit.

![Cache miss.](Read-through%20Caching%20Strategy/Untitled%201.png)

Cache miss.

```jsx
async function getBooksByAuthorId(cache, db, authorId) {
	let result;

	try {
		// Let's assume the cache API understands how to transform
		// this invocation into an SQL statement
		result = await cache.get("find:bookReview", authorId);

		return result;
	} catch (error) {
		throw new QueryError("getBooksByAuthorId");
	}
}
```

## Pros

- Best case scenario involves 1 read operation.
- Resilient to database failures.
- Works for throughput workloads that require frequent reads.
- Consistency can be guaranteed if used in conjunction with [[Write-through Caching Strategy|write-through]] strategy.

## Cons

- Cache nodes do not have data until read. This happens when scaling or restoring from failures.
- Worst case scenario involves 2 read and 1 write operation. This happens when a key is looked up for the first time or has been removed (TTL).