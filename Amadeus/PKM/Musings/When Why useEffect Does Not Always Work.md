---
note-type: "Literature"
author: "Harry Brundage"
primary-zettelkasten-area: "React"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "October 18, 2022 12:58 AM"
sources: "Ryan Florence’s Use Effect Tweet"
---

# When/Why useEffect Does Not Always Work?

`useEffect` is not the ideal tool when trying to trigger a side effect given a specific user action, those are better inside tent handlers.

> *It's perfect for synchronizing state to a side-effect. It's not great at performing a side-effect given a specific action. ie, focus management. You want to focus after specific actions. Hard to model with synchronization. (For example, initial page load)*
> 

[https://twitter.com/ryanflorence/status/1222248031644340224?s=20](https://twitter.com/ryanflorence/status/1222248031644340224?s=20)