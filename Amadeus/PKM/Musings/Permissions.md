---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "IAM"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 11, 2022 1:44 AM"
Sources: "Unknown"
---

# Permissions

Permissions are rules that dictate what the entity is allowed to do. They are written in JSON, however [[Amadeus/PKM/Musings/What Is AWS|AWS]] provides a visual assitance UI to create them.

<aside>
⚠️ By default, no permissions are granted to any identity.

</aside>

```json
{
	"Version": "2012-10-17",
	// Permissions can have multiple statements
	"Statement": [
		{
			// Whether it allows or denies the operation.
			"Effect": "Allow",
			// Who this policy applies to.
			"Principal": {
				"AWS": ["arn:aws:iam:123:root"],
			},
			// Affected actions (They are service specific)
			"Action": "ec2:describe",
			// The object that exists (within the service) to which this policy applies to.
			"Resource": "*"
		}
	]
}
```

<aside>
<img src="https://app.notion.com/icons/subtitles_purple.svg" alt="https://app.notion.com/icons/subtitles_purple.svg" width="40px" /> Principle of Least Power: Never provide entities more permissions than needed. This applies to using the root account, having programmatic access keys (for the CLI and SDKs) and giving too  much power to users via policies.

</aside>

<aside>
⚠️ If two permissions are added to the same entity and they clash, e.g. one allows an action and one denies the same action. The final permission set will be the latter. Denies are stronger than allows.

</aside>

<aside>
<img src="https://app.notion.com/icons/skull_pink.svg" alt="https://app.notion.com/icons/skull_pink.svg" width="40px" /> Delete programmatic access keys from your root account.

</aside>