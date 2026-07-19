---
Note Type: "Literature"
Author: "Jamie Kyle"
Primary Zettelkasten Area: "Problem Solving"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Decouple Decision From Execution"
---

# “Decide What To Do” Then “Act On It”

This is a basic problem solving framework that works wonders in many situations. When I want to “*perform something*”,  first try to understand “w*hat needs to be done*”. Once that is understood, we just need to act on executing it.

In programming is quite similar, combining control flow logic with decision making, you can get convoluted code. This is why we could try splitting them into:

1. Deciding what you want to do.
2. Actually doing that thing.

> *General programming advice that goes for everyone regardless of your language or framework
However you wanna go about it, find a way to separate:
1. Deciding what you want to do
2. Actually doing that thing
Code that does both at the same time will be harder to unwind later*
> 
> 
> ```bash
> // make data
> let nextFocusIndex = null
> let nextClickIndex = null
> 
> if (event.code === "ArrowUp" || event.code === "ArrowLeft") {
>   nextFocusIndex = focusIndex <= 0 ? elements.length - 1 : focusIndex - 1
> } else if (event.code === "ArrowDown" || event.code === "ArrowRight") {
>   nextFocusIndex = focusIndex >= elements.length - 1 ? 0 : focusIndex + 1
> } else if (event.code === "Space") {
>   nextClickIndex = focusIndex
> }
> 
> // do stuff
> if (nextFocusIndex != null) {
>   event.preventDefault()
>   elements[nextFocusedIndex].focus()
> }
> 
> if (nextClickIndex != null) {
>   event.preventDefault()
>   elements[nextClickedIndex].click()
> }
> ```
> 

[https://twitter.com/buildsghost/status/1396614269605617665?s=20](https://twitter.com/buildsghost/status/1396614269605617665?s=20)