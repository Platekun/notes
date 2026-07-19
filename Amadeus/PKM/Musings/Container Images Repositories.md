---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Docker"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 4, 2022 1:37 AM"
Sources: "Unknown"
---

# Container Images Repositories

When working with containers, we have to be creating multiple images of our project. These images are stored locally and they are useful as long as we only need to create containers in our machine.

However the biggest benefit of using containers is having a consistent deployment experience. To accomplish this, we have to use external services like [[Amadeus/PKM/Musings/What Is AWS|AWS]]’ [[Amadeus/PKM/Musings/What Is ECS|ECS]] to help us create [[Amadeus/PKM/Musings/What Are Containers|containers]]. And in order to use those [[Container Images Repositories|container]] deployment services we have to share our [[Amadeus/PKM/Musings/What Is An Image|images]] with them using a specialized storage server called a “*repository*”. Container image repositories are servers whose main purpose is the sharing and distribution of container images.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Examples of container image repositories services are [Dockerhub](https://hub.docker.com) and [[Amadeus/PKM/Musings/What Is ECR|ECR]].

</aside>