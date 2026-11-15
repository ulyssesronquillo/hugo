---
title: 'aws terraform security group'
author: ulysses

date: 2022-01-04
slug: aws-terraform-security-group
draft: false
---

How to create AWS security groups using Terraform.

```
resource "aws_security_group" "my-security-group" {
  name        = "my-security-group"
  description = "allow ports"
  vpc_id      = aws_vpc.my-vpc.id

  ingress {
    description = "ping"
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
    description = "http"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
    description = "https"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "ALL"
    cidr_blocks = ["0.0.0.0/0"]
  }
  tags = {
    Name = "my-security-group"
  }
}
```