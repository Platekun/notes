# Private Subnetwork

A private subnet does not have connection to the internet gateway and therefore the resources within the subnet only able to talk to each other and to other instances inside the [[What Is A VPC|VPC]].

Resources inside a private subnet that need internet access will have to use a Network Address Translation (also known as NAT) Gateway however it only works for outgoing traffic.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Resources inside a private subnet are not supposed to have a [[Public IP Addresses|public IP addresses]].

</aside>