---
title: 'aws assume role'
author: ulysses

date: 2019-05-23
slug: aws-assume-role
draft: false
---

If you have multiple AWS accounts, you can gain additional permission by authorizing it to a different AWS account via IAM. Here’s the [assume role](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html) documentation from AWS. And here are some documentation if you need to grant someone to [switch](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_permissions-to-switch.html) accounts. If you are going to be using the AWS CLI, you will need to run “aws configure” to setup multiple profiles.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": "sts:AssumeRole",
            "Resource": [
                "arn:aws:iam::*:role/your-custom-role"
            ],
            "Effect": "Allow"
        }
    ]
}
```