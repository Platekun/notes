---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Databases"
secondary-zettelkasten-area: "Distributed Programming"
status: "Processed"
sources: "Distributed Database Definition, \"Can replication and duplication be considered consensus protocols in distributed databases?” Prompt, “Do distributed databases use replication and duplication?” Prompt, “How is it different from database duplication?” Prompt"
---

# What Is Database Duplication?

Database duplication is an technique in [[What Is Distributed Consensus|distributed consensus]] that consists in identifying a leader database and duplicating it on given a window of time. This ensures high data consistency on a distributed system. However it limits clients to only modify the identified leader database.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> It is not considered a consensus protocol (since nodes in the system do not agree on a value) but rather an alternative to it.

</aside>