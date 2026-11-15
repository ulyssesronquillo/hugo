---
title: 'aws terraform create policy and attach'
author: ulysses

date: 2023-06-21
slug: aws-terraform-create-policy-and-attach
draft: false
---

Here’s the Terraform code that creates an AWS IAM policy and attaches it to an existing role (ROLENAME).

```
# CREDENTIALS
provider "aws" {
  shared_credentials_files = ["~/.aws/credentials"]
  shared_config_files      = ["~/.aws/config"]
  profile                  = "default"
  region                   = "us-east-1"
}
# CREATE POLICY
resource "aws_iam_policy" "s3-policy" {
    name        = "s3-policy"
    description = "Allow role to write to bucket"
    policy = "${file("policy.json")}"
}
# ATTACH POLICY TO ROLE
resource "aws_iam_role_policy_attachment" "s3-policy-attachment" {
  role       = "ROLENAME"
  policy_arn = aws_iam_policy.s3-policy.arn
}
```

Here’s the policy.json file.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:PutObjectAcl",
                "s3:ListBucket",
                "s3:GetBucketLocation",
                "s3:GetObject",
                "s3:GetObjectAcl",
                "s3:DeleteObject"
             ],
            "Resource":"arn:aws:s3:::your-bucket/*"
            }
        }
    ]
}
```