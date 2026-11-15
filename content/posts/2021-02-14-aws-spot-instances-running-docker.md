---
title: 'aws spot instances running docker'
author: ulysses

date: 2021-02-14
slug: aws-spot-instances-running-docker
draft: false
---

I have an AMI with docker installed. Here’s how I launch a spot instance using Terraform.

Here’s my Terraform script.

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
resource "aws_spot_instance_request" "docker" {
  ami                           = "ami-xxxxxxxxxxxxxxxx"
  spot_price                    = "0.0031"
  wait_for_fulfillment          = "true"
  key_name                      = "servers"
  instance_type                 = "t3.micro"
  subnet_id                     = "subnet-xxxxxxxxxxxxxxxx"
  security_groups               = ["sg-xxxxxxxxxxxxxxxxxx"]
  associate_public_ip_address   = "true"
  user_data = 
```

I use "aws_ec2_tag" resource to tag the instance properly.

In addition, I use user_data to run a script, to set the hostname.

To launch via Terraform, I run the following commands.</p>

```
terraform init
terraform apply
```

When done, I could stop the instance to stop incurring charges. Or just simply destroy it via Terraform.

```
terraform destroy
```

It's not bad deal for an instance that costs only $0.0031 per hour.