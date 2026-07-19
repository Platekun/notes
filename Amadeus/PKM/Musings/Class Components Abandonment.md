---
Note Type: "Literature"
Author: "Yehuda Katz"
Primary Zettelkasten Area: "Developer Mindset"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Front-End Development, Design Patterns"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Class Components Abandonment Tweet"
---

# Class Components Abandonment

We have arrived to a point in time where we threw away a language feature used to to describe blueprints we attempt to create functions that have state that is somehow remembered by the system, something like “*runtime classes*”. It feels like these developers have given up using classes for components for dogmatic reasons ([‣](https://app.notion.com/p/ae3c78e9d7a543ebadd57af3949c7bcf?pvs=21)).

> *To be honest, it seems like people have given up on trying to use classes and instances to model components for largely religious reasons, and use details of prior implementations, and Very Serious Arguments as excuses to ignore them.

Instead of using the language feature for describing a blueprint and creating instances of it (classes), we're trying to turn functions into classes by moving the concept of the "instance" into the runtime (hooks) or turning modules into classes by eliminating singleton-ness*
> 

[https://twitter.com/wycats/status/1280555846397657088?s=20](https://twitter.com/wycats/status/1280555846397657088?s=20)

[https://twitter.com/wycats/status/1280556444568268800](https://twitter.com/wycats/status/1280556444568268800)