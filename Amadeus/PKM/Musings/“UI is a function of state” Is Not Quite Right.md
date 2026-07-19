---
Note Type: "Literature"
Author: "Jamie Kyle"
Primary Zettelkasten Area: "React"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset, Front-End Development"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "A Wrong Perspective On UI"
---

# “UI is a function of state” Is Not Quite Right

“UI is a function of state” was a popular catchphrase mentioned by Pete Hunt when React was presented. After some time there are options that critique that it taught people that React was not a good place for placing certain kind of state. This opinions considers React as a state management library instead of a view library which is why they consider any state outside React as “error-prone”. They accept the existence of such external state as a necessary evil however they try to interact with it via hooks to avoid leaking implementations.

> *"UI is a function of state" was a terrible way to teach people React, it taught people state in React was something to avoid instead of the best place for it

Today I treat any state outside of React as something I have to tightly control and worry about as a source of bugs in my app. As soon as I possibly can I wrap it in a hook to quarantine (sorry) it.

There are extreme cases where I need to get out of the React lifecycle for performance reasons. But in those rare cases I try to take the minimal amount of code out of React and then immediately wrap it with a hook, treating it as a private implementation not usable on its own*
> 

[https://twitter.com/buildsghost/status/1265727209169227777](https://twitter.com/buildsghost/status/1265727209169227777)

[https://twitter.com/buildsghost/status/1265727957068214272?s=20](https://twitter.com/buildsghost/status/1265727957068214272?s=20)

[https://twitter.com/buildsghost/status/1265728607579549696?s=20](https://twitter.com/buildsghost/status/1265728607579549696?s=20)