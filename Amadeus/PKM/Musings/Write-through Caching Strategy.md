---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 27, 2022 1:30 AM"
Sources: "Things You Should Know About Database Caching"
---

# Write-through Caching Strategy

In this cache strategy the application is responsible for writing to the cache, while the cache is responsible for writing the data to the database.

![Untitled](Write-through%20Caching%20Strategy/Untitled.png)

```jsx
async function createBookReview(cache, createCommentInput) {
	let result;

	try {
		// Let's assume the cache API understands how to transform
		// this invocation into an SQL statement
		result = await cache.write("new:bookReview", createCommentInput);

		return result;
	} catch (error) {
		throw new QueryError("createBookReview");
	}
}
```

## Pros

- Best case scenario involves 2 write operations.
- Cache will be always fresh.
- Consistency can be guaranteed if used in conjunction with [[Read-through Caching Strategy|read-through]] strategy or [[Cache-Aside Caching Strategy|cache-aside]].

## Cons

- Cache nodes do not have data until written. This happens when scaling or restoring from failures.
- High latency. However users tend to accept higher response times with write operations.
- Not resilient to database failures.
- Not all of the cached data will be used.