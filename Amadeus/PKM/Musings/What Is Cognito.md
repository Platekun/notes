---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Cognito"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 10, 2022 12:00 AM"
Sources: "Unknown"
---

# What Is Cognito?

The Cognito service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to manage user data across multiple devices.

Cognito’s business model revolves around creating user pools for users of our applications where they can sign up and sign in with their with their credentials or third-party identity providers like Facebook, Google, Amazon or Apple.

Cognito uses two key concepts:

- “*user pools*”: A user directory that provides authentication features.
- “*identity pools*”: A directory that grants authorization to users to use services.

While we lose control of our infrastructure we still have some configuration settings we can customize like:  password policies, multi-factor authentication, account recovery, notifications and even permissions to use other services.

![Untitled](What%20Is%20Cognito/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/cognito/v2/home?region=us-east-1#)