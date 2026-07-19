---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Lambda"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 2, 2022 1:43 AM"
Sources: "Unknown"
---

# What Is Lambda?

The Lambda service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to execute functions in reaction to certain event triggers.

In order to use Lambda  we have to provide our code via the online editor, a zip file or a docker container (It has support for multiple runtimes). While we lose control of our infrastructure we still have some configuration settings we can customize like: CPU, storage, timeouts, [[Permissions|IAM permissions]], [[Roles|IAM roles]], [[Amadeus/PKM/Musings/What Is EFS|extra file systems]].

To execute our code Lambda needs an event trigger (an integration with other [[Amadeus/PKM/Musings/What Is AWS|AWS]]) which will route the request to Lambda which eventually will execute our function. An example of an event trigger is a file being uploaded to [[What Is S3|S3]].

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Lambda is referred as “*Functions-as-a-Service*” (also known as FaaS).

</aside>

![Untitled](What%20Is%20Lambda/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/lambda/home?region=us-east-1#/discover)