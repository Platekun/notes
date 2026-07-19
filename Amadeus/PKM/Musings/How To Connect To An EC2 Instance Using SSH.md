---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "EC2"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "September 27, 2022 1:07 AM"
Sources: "Unknown"
---

# How To Connect To An EC2 Instance Using SSH

## Prerequisites

1. Locate the private key of the [[What is EC2|EC2]] instance in your machine.
2. Grab the user name to connect with to the [[What is EC2|EC2]] instance.
3. Grab the Public DNS (See [[How To Find Details Of An EC2 Instance]] ) of the [[What is EC2|EC2]] instance.
4. Make sure the status checks of the [[What is EC2|EC2]] instance has passed (See the “*Status Check*”) column.

## Steps

1. Open up the terminal.
2. Navigate where your private key is located.
3. Set the permissions to the private key:
    
    ```bash
    $ chmod 400 [private-key-name].pem
    ```
    
4. Connect to the EC2 instance using:

```bash
$ ssh -i [private-key-name].pem [user-name]@[public-dns-ip-address]
```

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Usually the user name is `ec2-user` however it can be different depending on the AMI used.

</aside>

To find the most recent instructions regarding connecting to an [[What is EC2|EC2]] instance using SSH follow these steps:

To get started navigate to the [[What is EC2|EC2]] home page:

[](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1)

![1. Navigate to the service home page and tap on “[*Instances*](What%20is%20EC2.md)”.](How%20To%20Create%20An%20EC2%20Instance%20That%20Does%20Something%20/Untitled.png)

1. Navigate to the service home page and tap on “[[What is EC2|*Instances*]]”.

![2. All instances of the region will be displayed here. Tap on the “*instance ID*” of an instance.](How%20To%20Find%20Details%20Of%20An%20EC2%20Instance/Untitled.png)

2. All instances of the region will be displayed here. Tap on the “*instance ID*” of an instance.

![3. Tap on “*Connect*”.](How%20To%20Find%20Details%20Of%20An%20EC2%20Instance/Untitled%201.png)

3. Tap on “*Connect*”.

![4. Tap on “*SSH Client*”.](How%20To%20Connect%20To%20An%20EC2%20Instance%20Using%20SSH/Untitled.png)

4. Tap on “*SSH Client*”.

![5. Follow each step.](How%20To%20Connect%20To%20An%20EC2%20Instance%20Using%20SSH/Untitled%201.png)

5. Follow each step.

## Read More

[Connect to your Linux instance using SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)