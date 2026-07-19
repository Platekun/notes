---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Caching"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Unprocessed"
created-time: "October 27, 2022 12:30 AM"
sources: "Things You Should Know About Database Caching"
---

# Application Caching Strategies

A caching strategy determines how the relationship between the database and the cache, and how the cached data is accessed.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> We should think about how our data will be accessed before designing our architecture.

</aside>

- [[Cache-Aside Caching Strategy|Cache aside]].
- [[Read-through Caching Strategy|Read-through]].
- [[Write-through Caching Strategy|Write-trough]].
- [[Write Behind Caching Strategy|Write behind]].
- Refresh-ahead