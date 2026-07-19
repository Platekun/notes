---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EC2"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 12, 2022 3:02 AM"
Sources: "Unknown"
---

# How To Create And Configure An EC2 Instance

To get started navigate to the [EC2](https://app.notion.com/p/3a184657277d4df885cb143114d9c8f8?pvs=21) home page:

[](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1)

![1A. Navigate to the service home page and tap on “[*Launch Instance*](https://app.notion.com/p/1cb29b21fbae4351ada8e40e668d46c0?pvs=21)”.](How%20To%20Create%20A%20Launch%20Configuration%20Template/Untitled.png)

1A. Navigate to the service home page and tap on “[*Launch Instance*](https://app.notion.com/p/1cb29b21fbae4351ada8e40e668d46c0?pvs=21)”.

![1B. Alternatively navigate to the service home page and tap on “*Instances*”, then tap on “*Launch Instances*”.](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled.png)

1B. Alternatively navigate to the service home page and tap on “*Instances*”, then tap on “*Launch Instances*”.

![2. Input the name of the new EC2 instance, select its [Amazon Machine Image (AMI)](https://app.notion.com/p/c516f9c3e6ae4751b0663336c81e9ebc?pvs=21) and the number of instances to be created.](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled%201.png)

2. Input the name of the new EC2 instance, select its [Amazon Machine Image (AMI)](https://app.notion.com/p/c516f9c3e6ae4751b0663336c81e9ebc?pvs=21) and the number of instances to be created.

![3. Select the [instance type](https://app.notion.com/p/d672a33a27fd44bba23d8cc1f26330cb?pvs=21).](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled%202.png)

3. Select the [instance type](https://app.notion.com/p/d672a33a27fd44bba23d8cc1f26330cb?pvs=21).

![4. Optionally input the name for a [key pair](https://app.notion.com/p/1ba241075890412a8e02d1a569917417?pvs=21) (or create a new one).](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled%203.png)

4. Optionally input the name for a [key pair](https://app.notion.com/p/1ba241075890412a8e02d1a569917417?pvs=21) (or create a new one).

![5. Input the network settings: You can configure the [VPC](https://app.notion.com/p/d21d3b2c41ef4da8a1a32ea11f3ec64b?pvs=21), subnet, IP address and [security groups](https://app.notion.com/p/37ebeaf430f24730846f57a98b0ef2cb?pvs=21).](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled%204.png)

5. Input the network settings: You can configure the [VPC](https://app.notion.com/p/d21d3b2c41ef4da8a1a32ea11f3ec64b?pvs=21), subnet, IP address and [security groups](https://app.notion.com/p/37ebeaf430f24730846f57a98b0ef2cb?pvs=21).

![6. Configure [storage](https://app.notion.com/p/9c4494fe67144f8e845597fa7e167be0?pvs=21) for the instance and submit the form by tapping on “*Launch Instance*”.](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled%205.png)

6. Configure [storage](https://app.notion.com/p/9c4494fe67144f8e845597fa7e167be0?pvs=21) for the instance and submit the form by tapping on “*Launch Instance*”.

<aside>
<img src="https://app.notion.com/icons/skull_pink.svg" alt="https://app.notion.com/icons/skull_pink.svg" width="40px" /> Be sure to terminate instances that you don’t need anymore.

</aside>