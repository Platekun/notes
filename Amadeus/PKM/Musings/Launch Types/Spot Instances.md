# Spot Instances

- Model: “*Bid*” for spare Instances which can be reclaimed any time.
- Billing: The instance spot will have a price depending on demand and if our bid is higher than the instance's price, we will be provisioned with the instance.
- Cons: We will lose the instance if the spot's price surpasses our bid.
- Use case: Fault tolerant workloads (Workloads that can be interrupted).
- Example: Batch jobs or random spikes.