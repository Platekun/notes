---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Networking"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 4, 2022 1:00 AM"
Sources: "Unknown"
---

# What Is CIDR?

The term is short for “*Classless Inter-Domain Routing*”. CIDR is a method which introduced a notation (known as “*CIDR Notation*”) to represent ranges of [[IP Addresses]] .

A CIDR notation looks like a normal [[IP Addresses]] with the addition of a slash followed by a number, referred as the “*network prefix*”. The network prefix represents the number of [[What Are Bits|What Are Bits?]]  that are fixed (meaning they do not change), for example:

```
CIDR: 10.0.0.0/24
Bits Fixed: 3x8 bits = 24 bits.
Range: 10.0.0.0 to 10.255.255.255
Total: 256 available addresses.

CIDR: 172.31.0.0 / 16
Bits Fixed: 2x8 bits = 16 bits.
Range: 172.31.0.0 to 172.31.255.255
Total: 65536 available addresses.

CIDR: 0.0.0.0/0 (Commonly used to refer as "Anywhere")
Bits Fixed: 0x8 bits = 0 bits.
Range: 0.0.0.0 to 255.255.255.255
Total: All possible addresses.
```