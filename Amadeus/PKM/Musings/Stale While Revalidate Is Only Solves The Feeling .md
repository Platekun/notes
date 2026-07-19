---
Note Type: "Literature"
Author: "Jamie Kyle"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "World Perception"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Stale While Revalidate Popularity Analysis"
---

# Stale While Revalidate Is Only Solves The Feeling Of Being Faster

Libraries such as SWR, React Query and Apollo are still too low-level when it comes to the bigger picture in the client-server gap. While the SWR pattern of fetching data could make things appear faster, it also missed the way users expect data to behave (most of times they want the latest data).

Key concepts like “*draft data*” and “*fetching from multiple sources*” are missing. There is also a missing link with navigation data and how cache should be cleared some times. 

Overusing the SWR pattern could produce over-fetching / data-usage.

[‣](https://app.notion.com/p/9f6ea940628546b086c34b192666aa9d?pvs=21) 

> *After using some of these newer React data fetching libraries a bit, I feel like the popularity of 'Stale While Revalidate' and automated invalidation of queries misses a lot of nuance about how users expect data to behave

For starters, and Ryan will absolutely appear in the replies to this, there needs to be a way to describe how data is expected to behave around navigation. Some data absolutely needs to be up to date all the time, other data (based on non-serialized state) needs to stay stale

There also needs to be concept of draft data in state managed by a data fetching framework. Which gets into a larger picture of needing multiple sources feeding data, and "revalidation" happening only when those sources can't provide up-to-date information

'Stale While Revalidate' is a nice way to make things seem faster than they are. But if you take it too far, you end up with obscene amounts of over-fetching/data-usage, and the experience ends up being very jarring. I spent a lot of time fighting these tools to make things nice*
> 

[https://twitter.com/buildsghost/status/1276012560970473472?s=20](https://twitter.com/buildsghost/status/1276012560970473472?s=20)

[https://twitter.com/buildsghost/status/1276013857811521541?s=20](https://twitter.com/buildsghost/status/1276013857811521541?s=20)

[https://twitter.com/buildsghost/status/1276015225427202049?s=20](https://twitter.com/buildsghost/status/1276015225427202049?s=20)

[https://twitter.com/buildsghost/status/1276015895039537154?s=20](https://twitter.com/buildsghost/status/1276015895039537154?s=20)