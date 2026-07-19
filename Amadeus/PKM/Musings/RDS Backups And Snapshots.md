---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "RDS"
status: "Processed"
sources: "Unknown"
---

# RDS Backups And Snapshots

RDS provides us with automatic backup our database. Database backups are performed daily during a maintenance window. They have a retention period of about 1 day in case we need to restore a previous version.

In case we need to perform a manual backup we can create a “*snapshot*” which can be stored indefinitely.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> RDS backups use [[EBS Snapshots|EBS volume snapshots]] under the hood.

</aside>