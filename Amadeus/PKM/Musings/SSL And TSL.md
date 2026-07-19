---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Networking"
status: "Processed"
sources: "Unknown"
---

# SSL And TSL

SSL stands for secure socket layer, and it is used to encrypt connections, and TSL stands for transport layer security which basically means it’s a new version of SSL. 

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> For all intents and purposes SSL works as an equivalent of TSL.

</aside>

These kind of certificates allow traffic between client and servers to be encrypted. The implementations details of how it works are complex but the summary is that these actors talk aback and forth with the “*authority*” to verify the certificate (The autorithy being Google, GoDaddy, Digicert, or any other company that sells certificates).

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> The process of decrypting the encrypted traffic with SSL / TSL before forwarding it to another server is called “*termination*”.

</aside>