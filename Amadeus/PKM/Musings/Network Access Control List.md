---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "VPC"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "September 29, 2022 12:21 AM"
sources: "Unknown"
---

# Network Access Control List

A network access control list (also known as NACL) is the equivalent of a [[Security Groups|security group]] in a [[Subnetworks|subnet]] level, they control inbound and outbound traffic using “*allow*” and “*deny*” rules.

Rules established by the NACL are supplied to all instances living in a [[Subnetworks|subnet]].

**Inbound rules example:**

| **Rule #** | **Type** | **Protocol** | **Range** | **Source** | **Allow / Deny** |
| --- | --- | --- | --- | --- | --- |
| 100 | HTTP (80) | TCP (6) | 80 | 0.0.0.0/0 | **ALLOW** |
| * | All IPv4 Traffic | All | All | 0.0.0.0/0 | **DENY** |

**Outbound rules example**:

| **Rule #** | **Type** | **Protocol** | **Range** | **Source** | **Allow / Deny** |
| --- | --- | --- | --- | --- | --- |
| 100 | HTTP (80) | TCP (6) | 80 | 0.0.0.0/0 | **ALLOW** |
| * | All IPv4 Traffic | All | All | 0.0.0.0/0 | **DENY** |
- Rules are evaluated based from the lower number to the highest. The lower number rules are applied first disregarding if a higher number rule tries to overwrite it.
- Rules tables have their last row inmutable (the one with the `*`) as it is considered a catch all.