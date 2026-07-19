---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 26, 2022 1:15 AM"
Sources: "Systems Design Primer"
---

# Application Caching

The term “*Application*” refers to the application layer in a three-tier architecture. The one in charge of processing the commands, performing logical desicions and processing data between the database and the user interface.

This type of caching is about using a database living between the application layer and the primary database instance. 

The key here is that the cache database is an in-memory database, one that runs on RAM which allows data retrievals to be fast. Examples of this are Memcached or Redis.

On this layer we can see there are two types data types which are good candidates for caching:

- Database queries: We can use the cache as a way to store our database query results. The query would be the `key` and the result would be the `value`.
- Runtime objects: If we treat cache the same way as our code, we can store our data sturctures in the cache (user sessions, rendered pages, activity st reams, user data).

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Implementing this type of caching requires source code to be modified.

</aside>