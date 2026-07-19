---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Systems Design"
last-edited-time: "September 20, 2023 2:23 AM"
secondary-zettelkasten-area: "Databases"
status: "Processed"
created-time: "October 22, 2022 1:16 AM"
sources: "Unknown"
---

# Self-Hosted Databases

The term “*self hosting”* refers to taking full control of the hosting aspect of our database. By taking full control of the database we also inherit full responsibility, which means we have to take care of:

- Installing all the needed software.
- Keeping it up to date.
- Managing backups.
- Time traveling using said backups.
- Securing it.
- Creating read replicas.
- Setting up disaster recovery.
- Scaling it horizontally.

There are valid reasons to take this approach like having experts at hand or having company protocols (difficult to change).