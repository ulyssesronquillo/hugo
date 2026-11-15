---
title: 'terraform launch ec2 instance'
author: ulysses

date: 2019-08-02
slug: terraform-launch-ec2-instance
draft: false
---

Here’s the template for launching an EC2 instance via Terraform.

```
provider "aws" {
  region                  = "us-east-1"
  shared_credentials_file = "/home/username/.aws/credentials"
  profile                 = "default"
}
resource "aws_security_group" "hostname-sg" {
	name = "allow ssh"
	vpc_id = ""
	ingress {
		cidr_blocks = [ "10.0.0.0/8" ]
		from_port = 22
		to_port = 22
		protocol = "tcp"
	}
	egress {
		from_port = 0
		to_port = 0
		protocol = "-1"
		cidr_blocks = [ "0.0.0.0/0" ]
	}
}
resource "aws_instance" "hostname" {
	ami = "ami-xxxxxxxxxx"
	key_name = "your-key"
	instance_type = "t2.large"
	subnet_id = "subnet-xxxxxxxx"
	security_groups	= ["${aws_security_group.hostname-sg.id}"]
	tags {
		Name = "hostname"
		Environment = "development"
	}
}
```