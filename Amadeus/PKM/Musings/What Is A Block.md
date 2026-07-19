---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Crypto"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "BlockChain"
Status: "Unprocessed"
Created time: "December 30, 2022 3:19 AM"
Sources: "Blockchain Definition, “How does transaction data look like in a blockchain block?” Prompt, “So in a PoW protocol, there is only one block being added. this block can contain the reward for the miner along with other transaction data?” Prompt"
---

# What Is A Block?

A block is a record in a [[What Is A Blockchain|blockchain]]. Records are inmutable, meaning that once created they cannot be destroyed. Blocks are added to a blockchain every time a solution [[What Is Distributed Consensus|proposed]] by a [[What Is A Worker Node|worker node]] reaches [[What Is Distributed Consensus|consensus]].

The details of what a block is made of depend on the [[What Is A Blockchain|blockchain]] that is being used, however we can identify:

- A timestamp: A string that represents when the record was created.
- A cryptographic hash: A unique identifier of the previous block.
- Transaction data:
    - The sender's "[[What Is An Address|*address*]]”.
    - The recipient's "[[What Is An Address|*address*]]”.
    - The [[What Is Proof-of-Work|winner]] [[What Is A Worker Node|worker]]'s "[[What Is An Address|*address*]]” and the amount of currency rewarded (assumming the use of a [[What Is Proof-of-Work|PoW protocol]]).
    - Transaction fees.

Since blocks contain information about the previous blocks, this means they are sort of "*linked*”.