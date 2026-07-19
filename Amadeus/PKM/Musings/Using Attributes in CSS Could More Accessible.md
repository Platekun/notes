---
Note Type: "Literature"
Author: "Jamie Kyle"
Primary Zettelkasten Area: "CSS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Accesible CSS Practices"
---

# Using Attributes in CSS Could More Accessible

Sometimes doing the hard thing the easy thing is the best way to go. Hypothetically, accesibility which is often neglected by many teams can be addressed if we wrote CSS files using ARIA attributes. Doing it in this way will require both styles to work and be accesible at the same time.

> *I think if you make it a rule to always use attributes instead of classes to apply CSS to element states (not variants), you’ll force yourself to make your app more accessible (Similar to React Testing Library)

If you’re using CSS-in-JS this also helps create more static styles*

Since its come up: There are places where you should use [aria-disabled] over [disabled]

The [disabled] attribute will remove elements from the accessibility tree hiding them from screen readers

Ex: disabled submit buttons while the form has errors should use [aria-disabled]
> 

[https://twitter.com/buildsghost/status/1389225898193293313?s=20](https://twitter.com/buildsghost/status/1389225898193293313?s=20)

[https://twitter.com/buildsghost/status/1389289220594757632?s=21](https://twitter.com/buildsghost/status/1389289220594757632?s=21)