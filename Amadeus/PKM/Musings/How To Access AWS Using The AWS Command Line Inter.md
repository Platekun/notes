---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "AWS"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "August 10, 2022 1:38 AM"
Sources: "Unknown"
---

# How To Access AWS Using The AWS Command Line Interface

AWS provides us with the AWS Command Line Interface (also known as AWS CLI) as an alternative mean to use their services. In order to use the CLI we have to set up our access key in a development machine.

The AWS CLI is command-driven and it can simplify repeated tasks for large-scale setups.

## Setup Instructions

<aside>
⚠️ You will need a pair of access keys which can only be generated through the web console in the [IAM service page](https://us-east-1.console.aws.amazon.com/iamv2/home).

</aside>

To download the AWS CLI visit:

[AWS Command Line Interface](https://aws.amazon.com/cli/)

Once installed, execute the following command to grant the AWS CLI access to your user credentials. 

```bash
$ aws configure
```

## Multiple Profiles

We can setup multiple profiles in our local machine with different sets of credentials by using:

```bash
$ aws configure --profile [[profile-name]]
```

## Multifactor Authentication

In order to use multifactor authentication (also known as MFA) with the AWS CLI we need to:

- Setup MFA with our AWS account.
- Obtain the amazon resource name of our MFA device (There are multiple types of MFA devices supported however the most common one is a Virtual MFA).
- Use the “*Security Token Service*” in order to get a temporary session.
    
    ```bash
    $ aws sts get-session token --serial-number [[arn]] --token-code [[mfa-code]]
    ```
    
- Configure a new profile with the newly temprary credentials.