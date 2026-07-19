---
Note Type: "Literature"
Author: "Yehuda Katz"
Primary Zettelkasten Area: "Object Oriented Programming"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Object Oriented Fear"
---

# Mutable State In Functions

Many developers HATE the word `class`. They immediately raise concerns about mutable state (even though React Hooks do the same). Yehuda found that when he inquired more about this critique they believe this cannot happen inside `functions` with.

> *I've noticed that functional programming adherents get turned off by the *keyword class* much more than any particular aspect of OO programming.
In contrast, people who like object oriented programming don't have a visceral dislike for the keyword function.

My experience is that people will often use the presence of the word "class" in a JS API as evidence that it will have more risky mutable state.
But React hooks give you just as much mutable state as the equivalent class structure.

A number of people have asked me whether Ember has something similar to Hooks because they prefer functional programming because of mutable state.
When I drill in, it becomes apparent that they're using the keyword "function" as a heuristic.*
> 

[https://twitter.com/wycats/status/1203060503997583360?s=20](https://twitter.com/wycats/status/1203060503997583360?s=20)

[https://twitter.com/wycats/status/1203062392441016320?s=20](https://twitter.com/wycats/status/1203062392441016320?s=20)

[https://twitter.com/wycats/status/1203062551199670272](https://twitter.com/wycats/status/1203062551199670272)