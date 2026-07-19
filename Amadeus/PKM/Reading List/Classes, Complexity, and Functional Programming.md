---
URL: "https://kentcdodds.com/blog/classes-complexity-and-functional-programming"
---

# Classes, Complexity, and Functional Programming

> The real benefit to notice here is that most of the properties for this `person` live on the `prototype` (shown as `__proto__` in the screenshot) rather than the instance of `person`. This is not insignificant because if we had ten thousand instances of `person` they would all be able to share a reference to the same methods rather than having ten thousand copies of those methods everywhere.
> 
> 
> ![](Classes%2C%20Complexity%2C%20and%20Functional%20Programming/0.png)
> 

> What I want to focus on now is how many concepts you have to learn to really understand this code and how much complexity those concepts add to your code.
> 

> My assertion is that `this` is hard to learn and can add unnecessary complexity to your codebase.
> 

> Note that functional programming is more about making code easier to understand so long as it's "fast enough." Despite speed of execution not being the focus, there are some reeeeally nice perf wins you *can* get in certain scenarios (like reliable `===` equality checks for objects for example). More often than not, **your use of functional programming will *often be way down on the list of bottlenecks that are making your application slow.***
> 

> Classes (and prototypes) have their place in JavaScript. But they're an optimization. They don't make your code simpler, they make it more complex. It's better to narrow your focus on things that are not only simple to learn but simple to understand: functions and objects.
>