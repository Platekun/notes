---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EC2"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 12, 2022 3:05 AM"
Sources: "Unknown"
---

# Security Groups

A security group is a set of rules that control the traffic that comes in or out of [[What is EC2|EC2]] instances. Their rules are always permissive (meaning they can’t restrict traffic) and they can only target [[Amadeus/PKM/Musings/IP Addresses/What Is An IP Address|IP addresses]] or other security groups (advance case, think of it like doing composition of firewalls).

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> By default the only inbound traffic allowed is SSH however all outbound traffic is enabled.

</aside>

![Untitled](Security%20Groups/Untitled.png)