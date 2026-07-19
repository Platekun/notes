---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Bitcoin"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "BlockChain"
Status: "Unprocessed"
Created time: "December 30, 2022 2:25 AM"
Sources: "Proof Of Work Definition, Distributed Ledger Definition, \"Who determines the reward in a proof-of-work protocol?” Prompt, Breaking Down Proof-of-Work Mining and 51% Attacks, \"Miners are looking to create blocks, and they will solve a challenge in order to do so. If they get it right they will take as many transactions from the pool and shove them inside, is this correct?” Prompt, \"How are transactions selected in that case?” Prompt, Mempool Definition"
---

# What Is Proof-of-Work?

Proof-of-work (Also known as PoW) is a type of [[What Is Distributed Consensus|leaderless consensus protocol]] used to prevent DDoS and spam attacks. PoW protocols were popularized by the invention of [[What Is Bitcoin|Bitcoin]].

PoW protocols work by requiring [[What Is A Worker Node|worker]] nodes, referred as "*miners*”, to propose their solution to a complex mathematical challenge. The solution of these challenges are then used to validate [[What Is Bookkeeping|transactions]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The challenge itself is used to determine a certain amount of energy and hardware capacity was used to solve it. They are easy to verify but hard to compute.

</aside>

When a [[What Is Bookkeeping|transaction]] occurs in the [[What Is A DLT|DLT]], the [[What Is Bookkeeping|transaction]] is treated as a message that is broadcasted to all the miner nodes in the [[What Is A DLT|DLT]]. They will store the unprocessed transaction in a "*holding area*” (referred as "*mempool*”) which can be described as a [[What Is A Dristributed Database|distributed database]] for pending [[What Is Bookkeeping|transactions]].

The miner nodes will then start solving the challenge and once a miner solves the challenge, it proposes its solution with the other nodes in the network (All nodes do this until a [[What Is Distributed Consensus|consensus]] is reached). The first miner to solve the problem and whose solution is agreed upon, is allowed to create the new record.

To create the new record in the [[What Is A DLT|DLT]], the winner miner node will select a set of the available [[What Is Bookkeeping|transactions]] from its “*holding area*” and will try to fit as many as possible. The max. size of the record and the strategy by which transactions are selected for the new record is determined by the [[What Is A DLT|DLT]], for example in [Bitcoin](https://app.notion.com/p/e9e9b6b74d27498a82c16d5ee1015880?pvs=21) transactions with higher fees will have higher priority when being processed.

Once determined which transactions will be in the new record of the [[What Is A DLT|DLT]]. The miner [[What Is Database Replication|broadcasts the new record]] to the other nodes in the network.

PoW protocols provide a “*reward*” to the first miner node that completes a challenge successfully. The details of the reward depend on the [[What Is A Dristributed Database|consensus protocol]] that is being used, e.g. in the [[What Is Bitcoin|Bitcoin]] PoW, miner nodes are rewarded by an [[What Is A Block|amount]] of [[What Is Bitcoin|Bitcoin]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Because the use of a "*holding area*” and a specific strategy to select transactions for new records, transactions within the [[What Is A DLT|DLT]] can have different completion times.

</aside>