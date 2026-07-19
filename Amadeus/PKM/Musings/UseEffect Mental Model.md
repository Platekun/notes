---
Note Type: "Literature"
Author: "Ryan Florence"
Primary Zettelkasten Area: "React"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Unknown"
---

# UseEffect Mental Model

React’s `useEffect` use case is “*given a state change, perform a side-effect”.* It is not *“given the user performed a specific action, perform a side-effect”.* For Example*:*

```jsx
userIsEscaping = useRef(false);

useEffect(() => {
	if (userIsEscaping.current) {
		userIsEscaping.current = false;
		focusButton();
	}
}, [isOpen]);

onKeyDown={(e) => {
	if (e.key == "Escape") {
		userIsEscaping.current = true;
		setIsOpen(true)
	}
}
```

If a user performs an action, then it would fit better to perform the side-effect inside the event handler instead of an `useEffect` . This would be an attempt to have idempotent logic inside a `useEffect`.

This is mental model seems like “*thinking in states*“.

There is a contradiction though, the initial page load of a page does not fit this model. There was no state change to speak of but we need a way to trigger a side-effect to load data so people use `useEffect` to bypass this.

> *It's perfect for synchronizing state to a side-effect.
It's not great at performing a side-effect given specific action.
ie, focus management. You want to focus after specific actions. Hard to model with synchronization. (For example, initial page load)*
> 

[https://twitter.com/bouwe/status/1222243687461261314?s=20](https://twitter.com/bouwe/status/1222243687461261314?s=20)

[https://twitter.com/ryanflorence/status/1222248031644340224?s=20](https://twitter.com/ryanflorence/status/1222248031644340224?s=20)

[https://twitter.com/ryanflorence/status/1222278013418528769?s=20](https://twitter.com/ryanflorence/status/1222278013418528769?s=20)