---
title: 'aws lightsail create terraform'
author: ulysses

date: 2021-01-18
slug: aws-lightsail-create-terraform
draft: false
---

Here’s how to launch a LightSail instance using Terraform. Create a main.tf file.

```
terraform {
  required_providers {
    aws = {
      version = >= 3.22.0"
      source = "hashicorp/aws"
    }
  }
}
provider "aws" {
  profile = "default"
  region  = "us-east-1"
}
resource "aws_lightsail_instance" "yourinstance" {
  name              = "yourinstance"
  availability_zone = "us-east-1a"
  blueprint_id      = "amazon_linux_2"
  bundle_id         = "nano_2_0"
}
```

To launch, run the following Terraform commands.

```
terraform init
terraform apply
```