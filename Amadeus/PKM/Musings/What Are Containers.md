---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Docker"
status: "Processed"
sources: "Unknown"
---

# What Are Containers?

A container is a software package that contains both the code to be executed and the runtime it is going to be executed on. Containers created from the same [[Amadeus/PKM/Musings/What Is An Image|image]] are identical, meaning they share the same behavior.

Because of their identical behavior, containers are used to create different environments of code execution (development, staging, production).

They are also used for onboarding purposes to ease the setup of a new developer’s machine. In case we needed to switch projects, this benefits also applies since they isolate setups needed from the host.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> There is no limit to the number of containers we can use, our application can have or more containers.

</aside>