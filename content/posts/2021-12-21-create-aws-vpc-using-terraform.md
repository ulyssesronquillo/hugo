---
title: 'create aws vpc using terraform'
author: ulysses

date: 2021-12-21
slug: create-aws-vpc-using-terraform
draft: false
---

Creating a VPC in AWS using Terraform. The script will do the following:

- Create a VPC
- Create a Subnet
- Create an Internet Gateway
- Create a route in the default route table using the Internet Gateway

Contents of main.tf

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
    }
  }
}

provider "aws" {
  profile = "tfc"
  region  = "us-west-1"
}

resource "aws_vpc" "my-vpc" {
  cidr_block       = "10.0.4.0/24"
  instance_tenancy = "default"
  tags = {
    Name = "my-vpc"
  }
}

resource "aws_subnet" "my-subnet" {
  vpc_id            = aws_vpc.my-vpc.id
  cidr_block        = "10.0.4.0/24"
  availability_zone = "us-west-1a"
  tags = {
    Name = "my-subnet-us-west-1a"
  }
}

resource "aws_internet_gateway" "my-igw" {
  vpc_id = aws_vpc.my-vpc.id
  tags = {
    Name = "my-internet-gateway"
  }
}

resource "aws_default_route_table" "my-rt" {
  default_route_table_id = aws_vpc.my-vpc.default_route_table_id
  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.my-igw.id
  }
  tags = {
    Name = "my-route-table"
  }
}
```