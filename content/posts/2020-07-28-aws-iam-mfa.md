---
title: 'aws iam mfa'
author: ulysses

date: 2020-07-28
slug: aws-iam-mfa
draft: false
---

Here’s how to give AWS IAM users the ability to manage their own (MFA) Multi Factor Authentication. MFA makes your AWS console secure. AWS IAM users will be able to turn on MFA, using virtual devices such as Google Authenticator to secure their cloud accounts. Here’s the policy.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowViewAccountInfo",
      "Effect": "Allow",
      "Action": "iam:ListVirtualMFADevices",
      "Resource": "*"
    },
    {
      "Sid": "AllowManageOwnVirtualMFADevice",
      "Effect": "Allow",
      "Action": [
        "iam:CreateVirtualMFADevice",
        "iam:DeleteVirtualMFADevice"
      ],
      "Resource": "arn:aws:iam::*:mfa/${aws:username}"
    },
    {
      "Sid": "AllowManageOwnUserMFA",
      "Effect": "Allow",
      "Action": [
        "iam:DeactivateMFADevice",
        "iam:EnableMFADevice",
        "iam:ListUsers",
        "iam:GetUser",
        "iam:ListMFADevices",
        "iam:ResyncMFADevice"
      ],
      "Resource": "arn:aws:iam::*:user/${aws:username}"
    }
  ]
}
```