---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Systems Design"
last-edited-time: "September 20, 2023 2:23 AM"
secondary-zettelkasten-area: "Distributed Programming"
status: "Processed"
created-time: "November 17, 2022 11:47 PM"
sources: "Unknown"
---

# Integration Services

An integration service is an intermediary used to perform communication between different “*processes*”.

Communication is entirely done by passing messages from one “*proccess*” to another one. The specifics of how the integration service handles these messages depend on the message-passing technique that is being followed:

- [[What Is PubSub|PubSub]].
- [[What Is A Message Queue|Message Queues]].
- [[What Is RPC|RPC]].
- [[What Is HTTP|HTTP]].
- GraphQL.