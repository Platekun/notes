---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "BlockChain"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Ethereum, Systems Design"
Status: "Unprocessed"
Created time: "January 3, 2023 1:11 AM"
Sources: "What is Proof of Stake (PoS)｜Explained For Beginners (../Sources/What%20is%20Proof%20of%20Stake%20(PoS)%EF%BD%9CExplained%20For%20Beginne%202f0c87f6de6141f69049270155641b0d.md), Proof-of-stake Definition, “How does the Proof-of-stake work?” Prompt, \"Where do validators obtain the transactions to put in a block in a pos protocol?” Prompt"
---

# What Is Proof-of-Stake?

Proof-of-stake (Also known as PoS) is a type of [[What Is Distributed Consensus|leaderless consensus protocol]] used to serve as an alternative to PoW protocols which does not rely on computational hardware while being more energy performant.

PoS protocols work by requiring [[What Is A Worker Node|worker]] nodes, referred as "*validators*”, to "*lock*” an amount of cryptocurrency in order to be selected to forge the next [[What Is A Block|block]] in the [[What Is A Blockchain|blockchain]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The cryptocurrency provided as collateral also serves as an incentive to prevent malicious actors from overtaking the pool of validator nodes as their currency will be taken away by the [[What Is A DLT|DLT]].

</aside>

When a [[What Is Bookkeeping|transaction]] occurs in the [[What Is A DLT|DLT]], the [[What Is Bookkeeping|transaction]] is treated as a message that is broadcasted to all the validator nodes in the [[What Is A DLT|DLT]]. They will store the unprocessed transaction in a "*holding area*” (referred as "*mempool*”) which can be described as a [[What Is A Dristributed Database|distributed database]] for pending [[What Is Bookkeeping|transactions]].

From all the validator nodes, one is selected to be the "*forger*” of the new [[What Is A Block|block]]. The details of how a validator node is selected is determined by the [[What Is A DLT|DLT]], the most known factor in [[What Is Ethereum|Ethereum]] is the amount of cryptocurrency they provide as collateral (also referred as “*stake*”).

To create the new record in the [[What Is A DLT|DLT]], the validator node will select a set of the available [[What Is Bookkeeping|transactions]] from its “*holding area*” and will try to fit as many as possible (It will validate and sign them). The max. size of the record and the strategy by which transactions are selected for the new record is determined by the [[What Is A DLT|DLT]], for example in [[What Is Ethereum|Ethereum]] transactions with higher fees will have higher priority when being processed but other factors like its complexity are taken into account.

Once determined which transactions will be in the new record of the [[What Is A DLT|DLT]]. The forger [[What Is Database Replication|broadcasts the new record]] to the other nodes in the network.

PoS protocols provide a “*reward*” to the validator that forges the block which are taken from the  transactions fees of the block. The details of the reward depend on the [[What Is A Dristributed Database|consensus protocol]] that is being used, e.g. in the [[What Is Ethereum|Ethereum]] PoS, validator nodes are rewarded by an [[What Is A Block|amount]] of [[What Is Ethereum|ETH]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Because the use of a "*holding area*” and a specific strategy to select transactions for new records, transactions within the [[What Is A DLT|DLT]] can have different completion times.

</aside>