---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Caching"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 26, 2022 2:08 AM"
Sources: "Caching, Systems Design Primer"
---

# What To Cache?

To get all the benefits of [[Amadeus/PKM/Musings/What Is Caching|caching]], it is important to understand what exactly needs to be cached. 

A [[Amadeus/PKM/Musings/What Is Caching|cache]] is considered as successful if it has a high number of “*hits*”, they represent the times the data was available at the moment it was requested by another node. [[Amadeus/PKM/Musings/What Is Caching|Cache]] “*misses*” are the exact opposite, they represent the times when the data is not present in the cache.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The idea is to have a high number of hits and low number of misses.

</aside>