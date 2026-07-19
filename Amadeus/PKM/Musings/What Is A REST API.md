---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Software Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Distributed Programming, Back-End Development"
Status: "Processed"
Created time: "November 8, 2022 11:51 PM"
Sources: "Unknown"
---

# What Is A REST API?

A Representational State Transfer (also known as REST) API is an [[What Is An HTTP API|HTTP API]] that defines a set of practices for sharing data between clients and servers:

- Client-server:  The client and server programs are isolated from one another. The client only knows about URLs and this allows them to evolve accordingly.
- Uniform Interface: A set of rules that need to be followed to obtain client-server independence (see client-server). In summary it establishes that an object (resource) must have a consistent URL representation.
- Stateless: All necessary information is supplied with the request, and no state is retained other than the contents saved and loaded.
- Cacheable: [[Amadeus/PKM/Musings/What Is Caching|Caching]] should be done when applicable.
- Layeredness: Clients do not have knowledge about the the rest of the architecture. They don’t know if they are sending a request to a a [[Load Balancing|load balancer]] or to a server.

![How REST APIs are used.](What%20Is%20A%20REST%20API/Untitled.png)

How REST APIs are used.