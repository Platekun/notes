---
Note Type: "Literature"
Author: "Oliver Ash"
Primary Zettelkasten Area: "Routing"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Router Side-Effects"
---

# What Should A Router Do When Navigating

A proposed approach is that router should restore the scroll position when transitioning. The act of transitioning should also display stale data with an SWR fetching pattern in the background. 

This seems to expand on [‣](https://app.notion.com/p/5923c474a98b4420aef644f2d22f0aab?pvs=21), [‣](https://app.notion.com/p/544a79d960a44c37b77a6e4109fb1d9a?pvs=21) and [‣](https://app.notion.com/p/56d0e09b050c4111a6850f056fc07c0c?pvs=21) .

> *History (back/forward) navigations should (1) restore scroll position + other ephemeral state that isn't part of the URL and (2) show the same stale data the user saw previously and then (optionally) revalidate in background. The Twitter app gets this right, most other apps don't*
> 

[https://twitter.com/OliverJAsh/status/1258690971509895168?s=20](https://twitter.com/OliverJAsh/status/1258690971509895168?s=20)