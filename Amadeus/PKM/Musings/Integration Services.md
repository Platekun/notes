---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Systems Design"
secondary-zettelkasten-area: "Distributed Programming"
status: "Processed"
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