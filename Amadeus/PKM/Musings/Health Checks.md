---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Systems Design"
status: "Processed"
sources: "Unknown"
---

# Health Checks

Health checks are a way of asking a particular system / service / server whether or not it is capable of performing more work successfuly.

The way we ask a server about this is by a request, usually sent via HTTP to an endpoint exposed by the target in question.

![When using HTTP, 2XX and 3XX responses are treated as healthy.](Health%20Checks/Untitled.png)

When using HTTP, 2XX and 3XX responses are treated as healthy.