---
title: 'terraform aws security group'
author: ulysses

date: 2021-11-15
slug: terraform-aws-security-group
draft: false
---

How to create a security group in AWS via Terraform.

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

resource "aws_security_group" "my_sg" {
  vpc_id       = "vpc-xxxxxxxxxxxxxxxxx"
  name         = "My Security Group"
  description  = "My Security Group"
  ingress {
	from_port   = 8088
	to_port     = 8088
        protocol    = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
  }
  egress {
        from_port   = 0
        to_port     = 0
        protocol    = "-1"
        cidr_blocks = ["0.0.0.0/0"]
  }
  tags = {
        Name = "My Security Group"
  }  
}
```