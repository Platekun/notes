---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ElastiCache"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 27, 2022 8:14 PM"
Sources: "Performance At Scale With Amazon Elasticache"
---

# ElastiCache Engines

ElastiCache has support for two database engines: [Redis](https://redis.io) and [Memcached](https://memcached.org).

## Using Redis

- Works as a more modern cache because of its feature set. Something similar to [[Amadeus/PKM/Musings/What Is RDS|RDS]].
- Horizontal scaling is done via replication.
- Provides [[Amadeus/PKM/Musings/What Is Multi AZ|Multi-AZ]] failovers.
- It has supports for [[Read Replicas|read replicas]].
- Can be backed up and restored.
- Provides high availability.

## Using  Memcached

- Works as a traditional cache as described in [[Application Caching|application caching]].
- Horizontal scaling is done via sharding.
- Does not have persistence of data.
- Does not have backups and nor restored.
- Provides somewhat of availability but not higher than using Redis.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> It is recommended to default to using Redis since it has a more solid feature set with a decent speed. Memcached is chosen for minimalistic reasons and being okay if data is lost.

</aside>