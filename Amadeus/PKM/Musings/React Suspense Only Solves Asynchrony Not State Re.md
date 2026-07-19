---
note-type: "Literature"
author: "David Kourshid"
primary-zettelkasten-area: "React"
status: "Processed"
sources: "Suspense-related Code Is Still Error-Prone"
---

# React Suspense Only Solves Asynchrony Not State Related Challenges

The React Suspense API will not solve state related problems. They are still there, just hidden behind an implicitly defined state chart.

> *Hate to be the bearer of bad news, but code that uses suspense is still error-prone (in different ways).
It doesn't eliminate errors/impossible states, it just gives you a different way to manage caching/asynchrony.*
> 

[https://twitter.com/DavidKPiano/status/1190265460710920195](https://twitter.com/DavidKPiano/status/1190265460710920195)