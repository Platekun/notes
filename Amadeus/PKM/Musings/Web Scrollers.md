---
Note Type: "Literature"
Author: "Malte Ubl"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Mobile Development"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Web Scrollers Tweet"
---

# Web Scrollers

There seems to be a scroller object on native apps and there is only one scroller per route/screen.

> *The main technical issue is that there is a notion of "primary scroller" that has magical properties like hiding the URL bar and which is a singleton instead of having 1 instance per route which is how native apps work. Having one scroller per route makes scroll restauration trivial, transitions easier, among many other things. There was a proposal to create something like document.rootScroller but it didn't get momentum*
> 

[https://twitter.com/cramforce/status/1258563422494396417?s=20](https://twitter.com/cramforce/status/1258563422494396417?s=20)