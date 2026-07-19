---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "EC2"
status: "Processed"
sources: "Unknown"
---

# User Data

The “*user data*” file is a bash script that can provided when creating an [[What is EC2|EC2]] instance. It is executed at boot time, meaning it only executes once (when it starts). This script can be used for anything: Installing software, downloading files, automation, logging, etc.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The user data script is ran with the root user.

</aside>