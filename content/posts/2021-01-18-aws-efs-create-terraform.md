---
title: 'aws efs create terraform'
author: ulysses

date: 2021-01-18
slug: aws-efs-create-terraform
draft: false
---

Here’s how to build an EFS file system using Terraform. Create a main.tf file.

```
terraform {
  required_providers {
    aws = {
      version = ">= 3.22.0"
      source = "hashicorp/aws"
    }
  }
}
provider "aws" {
  profile = "default"
  region  = "us-east-1"
}
resource "aws_efs_file_system" "efs-test" {
   creation_token = "efs-test"
   performance_mode = "generalPurpose"
   throughput_mode = "bursting"
   encrypted = "true"
 tags = {
     Name = "efs-test"
   }
}
resource "aws_efs_mount_target" "efs-mt-example" {
   file_system_id  = aws_efs_file_system.efs-test.id
   subnet_id = "subnet-xxxxxxxxxxxxxxxxx"
   security_groups = ["sg-xxxxxxxxxxxxxxxxxx"]
}
```

To launch, run terraform.

```
terraform init
terraform apply
```