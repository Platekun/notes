---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ECS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "November 3, 2022 12:13 AM"
Sources: "Unknown"
---

# What Is ECS?

The Elastic Container (Also known as ECS) service is a service provided by [[Amadeus/PKM/Musings/What Is AWS|AWS]] used to create and manage [[Amadeus/PKM/Musings/What Are Containers|containers]] clusters. ECS uses [[What Is Docker|Docker]] under the hood, and its goal is to create a consistent deployment experience.

ECS needs to be provided a cluster structure: We have to [[Amadeus/PKM/Musings/What Is A Task Definition|define our tasks]] and [[Amadeus/PKM/Musings/What Are Containers|image]] configurations. The cluster structure also needs to know how infrastructure is going to be provided ([[What is EC2|EC2]] instances, [[Amadeus/PKM/Musings/What Is Fargate|Fargate]] and On-site servers).

![Untitled](What%20Is%20ECS/Untitled.png)

[](https://us-east-1.console.aws.amazon.com/ecs/home?region=us-east-1#/getStarted)