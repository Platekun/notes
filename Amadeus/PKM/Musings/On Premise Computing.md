---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Systems Design"
secondary-zettelkasten-area: "Cloud Computing"
status: "Processed"
sources: "Unknown"
---

# On Premise Computing

The term “*on premise*” refers to the practice of owning and operating our own data / centers hardware.

## Advantages

- We have full control over physical infrastructure and hardware.
- We have knowledge of the exact location of the hardware and data.

## Disadvantages

- We are responsible of maintaining the infrastructure which becomes complex [[Vertical Scalability|when the infrastructure grows]].
- We are responsible for long term planning of the [[Horizontal Scalability|capacity]] and possible [[Vertical Scalability|upgrades]] of the infrastructure because they need to be purchased, connected and installed.
- We are responsible of the security of the infrastructure, that includes physical security like [[Reliability|protection against catastrophes]].
- There is no easy way to react quickly to [[Scalability|workload spikes]].
- Idle resources can generate extra costs.
- We have a limited pool of physical locations to store our infrastructure.