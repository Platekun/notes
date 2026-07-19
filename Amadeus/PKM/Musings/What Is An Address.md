---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "BlockChain"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Unprocessed"
Created time: "January 5, 2023 2:11 AM"
Sources: "What is P2PK, P2PKH, P2SH, P2WPKH - ELI5?, What Is P2PKH?"
---

# What Is An Address?

An “[[What Is A Block|*address*]]” can mean be different things depending on the way transactions were made:

- **Pay To Public Key (P2PK):** Type of [[What Is Bookkeeping|transaction]] that requires a valid signature (using a [[How Is Access Represented In Crypto|private key]]) and a [[How Is Access Represented In Crypto|public key]]. They are the original type of addresses within [[What Is Bitcoin|Bitcoin]].
- **Pay To Public Key Hash (P2PKH):** Type of [[What Is Bookkeeping|transaction]] that does not conceals [[How Is Access Represented In Crypto|public keys]] but a hash of them. The address is a hash of the [[How Is Access Represented In Crypto|public key]]. They are the default type of address used by most nowadays [[What Is A Crypto Wallet|crypto wallets]].
- **Pay To Script Hash (P2SH):** Type of [[What Is Bookkeeping|transaction]] that that checks for multiple signatures before accepting the transaction. They are the type of address used by multi-signature wallets.
- **Pay To Witness Public Key Hash (P2WPKH).**