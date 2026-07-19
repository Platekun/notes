---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "RDS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 25, 2022 1:07 AM"
Sources: "Unknown"
---

# RDS Encryption

[[Amadeus/PKM/Musings/What Is RDS|RDS]] can encrypt database instances, backups, snapshots and read replicas. It uses the `AES-256` algorithm to perform this encryption.

## Limitations

- Encryption must be configured before creating an instance.
- If an instance is not encrypted, neither will the read replicas.

(There are more limitations to these two…)

## Unencrypted → Encrypted

There is a trick into encrypting an unencrypted [[Amadeus/PKM/Musings/What Is RDS|RDS]] instance. We can use an [[Amadeus/PKM/Musings/What Is EBS|EBS volume]] to create a copy of our instance. Then we encrypt that copy and restore a new instance out of it.