---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ELB"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 6, 2022 2:22 AM"
Sources: "Unknown"
---

# Connection Draining

When an resource gets deregistered from a load balancer while still having pending requests, the resource will complete those pending requests while the load balancer will not send new traffic to that resource.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> This also happens when a [[Health Checks|health checks]] fails.

</aside>