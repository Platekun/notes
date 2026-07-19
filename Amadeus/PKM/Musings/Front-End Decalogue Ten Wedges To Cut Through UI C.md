---
Note Type: "Fleeting"
Author: "Carlos Lobo"
Last edited time: "April 7, 2025 3:33 AM"
Status: "Unprocessed"
Created time: "April 7, 2025 2:35 AM"
---

# Front-End Decalogue: Ten Wedges To Cut Through UI Complexity

![7B99A14B-DDBB-487B-B134-27EDEB00CB89.jpeg](Front-End%20Decalogue%20Ten%20Wedges%20To%20Cut%20Through%20UI%20C/7B99A14B-DDBB-487B-B134-27EDEB00CB89.jpeg)

## 1st Wedge

It is forbidden for logic to rely on props, state, or styles not passed through the component’s API or intentionally layered.

> Hidden state is a ghost. Implicit styling is a curse.
> 
> 
> If a component moves and breaks, you summoned a witch.
> 
> The shape of a component must be self-evident. Its source of truth must be explicit. No hidden context. No magical dependencies. If it’s used, it must be imported or declared.
> 

## 2nd Wedge

It is forbidden to resolve UI bugs through non-deterministic fixes.

> A bug is not solved because it "*stopped happening.*" A layout is not valid because it "*looks fine now.*" A race condition is not closed because you "*moved the state higher.*". Every fix must be verifiable, observable, and grounded in known behavior.
> 

Using unstable timing, random fixes, or framework behavior you don’t control as a way to make the UI behave. It’s not that you don’t understand the pattern — it’s that you **didn’t *solve* the problem**, you just appeased it.

### 🚫 Use Case:

- “*I don’t know why this fixed it, but it works now.*”
- “*Adding this timeout made the glitch go away.*”
- “*I just memoized it and the warning disappeared.*”
- “*I wrapped it in a setTimeout. Don’t ask.*”

### 🔍 Where to apply:

- Fixing visual bugs or race conditions.
- Writing effect chains or animation logic.
- Debugging layout shifts or hydration mismatches.
- Dealing with async rendering or suspense.

## 3rd Wedge

It is forbidden to force consumers to rely on hidden workarounds or undocumented overrides. 

> Components must expose intentional escape hatches for behavior, structure, and styling.
> 

> It is forbidden to use patterns or hard to understand abstractions. All logic must be traceable, testable, and free of unnecessary cleverness.
> 

This decalogue was created to assist any front-end.

It is forbidden for supernatural agencies to be employed as a detective technique.

![image.png](Front-End%20Decalogue%20Ten%20Wedges%20To%20Cut%20Through%20UI%20C/image.png)