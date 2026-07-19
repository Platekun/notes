---
Note Type: "Literature"
Author: "Ryan Florence"
Primary Zettelkasten Area: "React"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "David K. Piano’s Mental Model For Effects Tweet"
---

# UseEffect’s Unnatural Mental Model

The first thing that comes to mind when observing a useEffect is “*something like an observable”*. This is a wrong impression however React docs make you believe we should think in terms of “*when X happens, execute this*”.

[‣](https://app.notion.com/p/1cd5b3baffc6491b80ef5dc975661856?pvs=21) could serve as a clearer mental model for UI side effects.

> *Yep, our mental model for effects is naturally "when X happens, execute this", which can be described declaratively!
The useEffect model of "execute this whenever X changes" is unnatural; that's why it's often accompanied with defensive programming inside (booleans).*
> 

[https://twitter.com/DavidKPiano/status/1404463903531225089](https://twitter.com/DavidKPiano/status/1404463903531225089)