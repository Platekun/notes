---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Databases"
status: "Processed"
sources: "What Is an Orphan Block?, Blockhain Definition, \"What is an orphan record in a DLT?” Prompt"
---

# What Is An Orphan Record?

An orphan record is a record in a [[What Is A DLT|DLT]] that was not accepted by its [[What Is A DLT|ledger]].

Orphan nodes are born when a node's solution does not reach [[What Is Distributed Consensus|consensus]]. There could be multiple reason why this happens: malicious actors trying to create a record, simultaneous records being created by two different [[What Is A Worker Node|worker]] nodes, etc.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> If represented in a linked list, orphan records look like forks that were made to the main chain of blocks (something like non-merged branches in a git repository).

</aside>