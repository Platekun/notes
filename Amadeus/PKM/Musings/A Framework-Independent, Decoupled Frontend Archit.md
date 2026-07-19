---
Note Type: "Literature"
Author: "Carlos Villuendas"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Front-End Development"
Status: "Processed"
Created time: "October 18, 2022 2:38 AM"
Sources: "A Framework-Independent, Decoupled Frontend Architecture For Large Scale Projects | T3chFest 2019"
---

# A Framework-Independent, Decoupled Frontend Architecture For Large Scale Projects | T3chFest 2019

![Untitled](A%20Framework-Independent%2C%20Decoupled%20Frontend%20Archit/Untitled.png)

Explained an example about how the architecture of [motos.net](http://motos.net/), [casas.net](http://casas.net/) and other market places from a company in Netherlands came to be after having a un-architectured pile of technologies.

At the beginning of the project the "*front-end architecture*" was simply jQuery, AKA no architecture at all, which brought a lot of headaches to the team because:

- **Spaghetti code**: What happens when you have a file with 13k Lines of Code? You usually have spread knowledge about the product and modifying any line can change the behavior in unexpected ways.
- **Unpredictable side-effects**: Changing things can cause strange effects. Since the knowledge is spread across a big file, the last person that touched that file is actually the one who should do the next task that involve that file causing bottlenecks.
- **Slow developer experience**: If your developers like working on your project it really helps because their productivity and innovation can skyrocket.
- Time to be productive is really long because it's almost impossible to get a good holistic picture of the product.

## **CTO Requests**

The CTO asked the team to improve all these issues while:

- **Business can't be stopped**: You cannot just stop producing just to perform a big rewrite.
- **SEO is unaltered**: The index-ability of the site should not be altered at all, it is a critical feature.

## Solution

![Untitled](A%20Framework-Independent%2C%20Decoupled%20Frontend%20Archit/Untitled%201.png)

### **Business Rules**

The team had to avoid having spread knowledge across the team, we have to locate those rules together. What's that knowledge? It's the knowledge that makes the product work, It's not the UI that's something volatile that changes a lot over time, We are talking about the business rules. **The business Rules are the soul of your product.**

- Calculations, validations, calls to other systems (AJAX, Cookies, Local Storage, Session Storage, etc.).
- Implementation: Hexagonal Architecture.
- Entities and value objects provide semantics to the app: Everything has a name and everybody understand what they are.
- Repositories (network, local storage, etc.) are just implementation details: This gives you power when you want to run code in different environments.
- Use cases give a name to your business rules → If they have no name then you have nothing.
- Stateless.
- Much easier to test, because it's decoupled from UI.
- **A place for everything and everything in its place.***

### **User Interface Components**

UI components knows almost nothing about the business rules.

- Site components:
    - They are specific to each site
    - They know how to talk to the site business rule to get information.
- SUI components:
    - They are open source
    - They know how to render information.

### **SUI Theme**

Collection of tokens meant to be overwritten. Shared language between design and front-end.

### **Site Theme**

Overwrites SUI-theme tokens to adapt them to the look-and-feel of the site.

### **Web Application**

- Wraps and gives coherence to the other layers.
- Imports each component's SASS file.
- Haves routing logic.
- Defines page components.
- SPA-like behavior.

The output of the compilation must work in a CDN