---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "AWS"
status: "Processed"
sources: "Unknown"
---

# Regions

## Global Infrastructure

AWS operates and owns data centers all over the world and these locations are called “*regions*” connected via their private network. Regions contain multiple data centers and have unique names ( e.g, `us-west-1` and `eu-west-2`).

Regions are physically isolated from each other in case a region is hit by a catastrophe, other regions are not affected by that.

## Regional Differences

- Different Pricing: Pricing as well can differ between regions because AWS have different costs for operating its infrastructure in different parts of the world. For this reason we must use AWS pricing calculator.
- Service Availability: Services offered by AWS are defined by their regions, meaning that not all regions offer all services. There are services that are available to everyone regardless of the region, these are called “*global*” services.
- Legal Reasons: There are companies which are legally required to use certain services in certain regions only (think EU user data).
- Availability and Latency: Picking the right region can makes difference in the user experience. This is why running applications as close to the end users is vital.