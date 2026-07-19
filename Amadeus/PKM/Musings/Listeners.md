---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "ELB"
status: "Processed"
sources: "Unknown"
---

# Listeners

A listener is a process that constantly checks of new incoming requests (Think of a router).

A listener rule is the action to be taken when an incoming request matches certain criteria (criteria we specify). [[Amadeus/PKM/Musings/What Is AWS|AWS]] allows for different types of listener rules (in the case of an application load balancer):

- Based in an URL path.
- Based in a hostname.
- Based on query strings.
- Based on request headers.

Listener rules are associated with a “[[Target Groups|***target group***]]” as their target.