---
title: 'aws move instance to another zone'
author: ulysses

date: 2021-12-23
slug: aws-move-instance-to-another-zone
draft: false
---

Here’s how to move an AWS instance to another zone.

Stop the instance first.

```
aws ec2 stop-instances --instance-ids i-1234567890abcdef0
```

Create an AMI image.

```
aws ec2 create-image \
--instance-id i-1234567890abcdef0 \
--name "my-ami" \
--description "my-ami"
```

Create EC2 instance using Terraform. The contents of main.tf.

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
    }
  }
}
provider "aws" {
  profile = "default"
  region  = "us-east-1"
}
resource "aws_instance" "ulysses" {
  ami                           = "ami-1234567890abcdef0"
  key_name                      = "servers"
  iam_instance_profile          = "machine-role"
  instance_type                 = "t3.micro"
  subnet_id                     = "subnet-1234567890abcdef0"
  security_groups               = ["sg-1234567890abcdef0", "sg-1234567890abcdef1"]
  tags = {
    Name = "moving-instance"
    tag1 = "test1"
    tag2 = "test2"
  }
}
```

Launch it.

```
terraform init
terraform plan
terraform apply
```