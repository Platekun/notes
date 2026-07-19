---
Note Type: "Literature"
Author: "Jamie Kyle"
Primary Zettelkasten Area: "Software Development"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Split Your User Type"
---

# Identity, Actors And Roles

Take the most common interface of them all, and the one nearly everyone gets wrong, `user`. User accounts are some of the most locked up objects around, and as a result, this is a prime candidate for breaking all the rules.

There are three things we usually use users for: Authentication, executing actions and managing permissions. Instead of using one interface for three actions, maybe we could consider three different interfaces:

- *“Identity” for authenticating.*
- *“Actor” for performing actions.*
- *“Role” for managing permissions.*

> *Do yourself a favor and split your “User” type into:
- “Identity” for authenticating
- “Actor” for performing actions
- “Role” for managing permissions
So tired of services that clearly hacked on features to an all powerful user type*
> 

[https://twitter.com/buildsghost/status/1400630504957775872](https://twitter.com/buildsghost/status/1400630504957775872)