---
Note Type: "Literature"
Author: "Yehuda Katz"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset, React"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "A Real Example Of “View As A Function OF State”"
---

# Ember Templates Are A Function Of State

A big difference between Ember and React is that Ember does not allow a window of time where component data / state is stale. Tracked properties allow to treat components as just JavaScript classes without worrying about having to create a projection.

There is certainly a period of time Ember takes to update the DOM after a mutation but the window of time is minimal. The mutation chain goes `Component → View`.

Ember templates actually behave as a function of state. They exist to reflect this output and not because of “*separations of concerns*”. 

> It matters a lot that Ember decided to never let you see "unrendered state"
You just scribble on you state as much as you want, you see the state changing in JS immediately 100% of the time, and Ember reflects it into the output "soon"

Sure. When you setState() in React (either class-based or hooks), you don't see the state you just changed until later.
In contrast, Ember tracked properties update immediately, and you can immediately read from them, just like any other JavaScript.

At some point after you've modified your JavaScript state, Ember revalidates the DOM using your templates.
Templates cannot directly mutate variables, so this makes a sharp separation between your input state and your "render function"

The model is: you react to JavaScript events by changing tracked state, using exactly the patterns you'd use in normal JavaScript, and without thinking about *when* your state is reflected.
Ember then takes your input state and reflects the changes based on your template.

In other words, templates aren't separate because of "separation of concerns" (whatever that means).
They're separate to distinguish *inputs* and *outputs*.
> 

[https://twitter.com/wycats/status/1189909669088620544?s=20](https://twitter.com/wycats/status/1189909669088620544?s=20)

[https://twitter.com/wycats/status/1190041037227446272?s=20](https://twitter.com/wycats/status/1190041037227446272?s=20)

[https://twitter.com/wycats/status/1190041427365040129?s=20](https://twitter.com/wycats/status/1190041427365040129?s=20)

[https://twitter.com/wycats/status/1190042061225037827?s=20](https://twitter.com/wycats/status/1190042061225037827?s=20)

[https://twitter.com/wycats/status/1190042264715845632?s=20](https://twitter.com/wycats/status/1190042264715845632?s=20)