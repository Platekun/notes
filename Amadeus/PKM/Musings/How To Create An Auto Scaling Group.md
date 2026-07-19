---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "ASG"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 11, 2022 1:06 AM"
Sources: "Unknown"
---

# How To Create An Auto Scaling Group

To get started navigate to the [EC2](https://app.notion.com/p/3a184657277d4df885cb143114d9c8f8?pvs=21) home page:

[](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1)

![1. Navigate to the service home page and then tap on “[Auto Scaling Groups](https://app.notion.com/p/f9bb4ca9059646c38943bc36d7ed6cb2?pvs=21)”.](How%20To%20Create%20A%20Launch%20Configuration%20Template/Untitled.png)

1. Navigate to the service home page and then tap on “[Auto Scaling Groups](https://app.notion.com/p/f9bb4ca9059646c38943bc36d7ed6cb2?pvs=21)”.

![2. Tap on “*Create auto Scaling group*”.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled.png)

2. Tap on “*Create auto Scaling group*”.

![3. Input the auto scaling group name and select the [launch template](https://app.notion.com/p/1a4e3c70da3140429bd5f6d583fc4ded?pvs=21). Tap “*Next*” to continue.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%201.png)

3. Input the auto scaling group name and select the [launch template](https://app.notion.com/p/1a4e3c70da3140429bd5f6d583fc4ded?pvs=21). Tap “*Next*” to continue.

![4. Input the network settings: You can configure the [VPC](https://app.notion.com/p/d21d3b2c41ef4da8a1a32ea11f3ec64b?pvs=21) and the [availability zones](https://app.notion.com/p/2efeeacd41de4f95826074ead5533b30?pvs=21). Optionally override the [launch template](https://app.notion.com/p/1a4e3c70da3140429bd5f6d583fc4ded?pvs=21).](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%202.png)

4. Input the network settings: You can configure the [VPC](https://app.notion.com/p/d21d3b2c41ef4da8a1a32ea11f3ec64b?pvs=21) and the [availability zones](https://app.notion.com/p/2efeeacd41de4f95826074ead5533b30?pvs=21). Optionally override the [launch template](https://app.notion.com/p/1a4e3c70da3140429bd5f6d583fc4ded?pvs=21).

![5. Optionally set the strategy to allocate the resources in the auto scaling group (advanced). Tap on “*Next*” to continue.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%203.png)

5. Optionally set the strategy to allocate the resources in the auto scaling group (advanced). Tap on “*Next*” to continue.

![6. Determine if a [load balancer](https://app.notion.com/p/82ca7a88d0ea46f4be2b8edc05472218?pvs=21) is needed. If needed we can attach [an existing one](https://app.notion.com/p/3d7e626494924b889afc4bb3b4a39782?pvs=21) or create one with with the new form that appears.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%204.png)

6. Determine if a [load balancer](https://app.notion.com/p/82ca7a88d0ea46f4be2b8edc05472218?pvs=21) is needed. If needed we can attach [an existing one](https://app.notion.com/p/3d7e626494924b889afc4bb3b4a39782?pvs=21) or create one with with the new form that appears.

![7. Decide the desired, minimum and maximum capacity for the aut oscaling group. Optionally specify the [scaling policies](https://app.notion.com/p/17fedb95a67749faafa27df5b22367e0?pvs=21). Tap on “*Next*” to continue.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%205.png)

7. Decide the desired, minimum and maximum capacity for the aut oscaling group. Optionally specify the [scaling policies](https://app.notion.com/p/17fedb95a67749faafa27df5b22367e0?pvs=21). Tap on “*Next*” to continue.

![8. Optionally add SNS notifications. Tap on “*Next*” to continue.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%206.png)

8. Optionally add SNS notifications. Tap on “*Next*” to continue.

![9. Optionally add tags. Tap on “*Next*” to continue.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%207.png)

9. Optionally add tags. Tap on “*Next*” to continue.

![10. Review the information for the auto scaling group. Submit the form by tapping on “*Create Auto Scaling group*”.](How%20To%20Create%20An%20Auto%20Scaling%20Group/Untitled%208.png)

10. Review the information for the auto scaling group. Submit the form by tapping on “*Create Auto Scaling group*”.