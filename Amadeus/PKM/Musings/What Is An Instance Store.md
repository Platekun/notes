---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EC2"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 12, 2022 10:11 PM"
Sources: "Unknown"
---

# What Is An Instance Store?

An instance store is an alternative storage option for [[What is EC2|EC2]] instances. An instance store uses a physical disk attached to the host computer which leads to a better I/O performance compared to a [[Network Drive|network drive]] offered with an [[Amadeus/PKM/Musings/What Is EBS|EBS]] volume.

The downside of using this alternative is that if the instance is stopped, all the data is lost.

Instance stores are a good use case for temporal data with frequent access but despite that it is not a recommended approach by [[Amadeus/PKM/Musings/What Is AWS|AWS]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Instance store compatibility is decided when choosing an AMI for the [[What is EC2|EC2]] instance.

</aside>