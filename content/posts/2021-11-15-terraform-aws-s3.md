---
title: 'terraform aws s3'
author: ulysses

date: 2021-11-15
slug: terraform-aws-s3
draft: false
---

How to create S3 bucket via Terraform.

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

resource "aws_s3_bucket" "bucket" {
  bucket = "my-ulysses-bucket"
  acl    = "private"

  tags = {
    Name        = "My Ulysses bucket"
    Environment = "Dev"
  }
}

resource "aws_s3_bucket_public_access_block" "example" {
  bucket = aws_s3_bucket.bucket.id
  block_public_acls = true
  block_public_policy = true
  ignore_public_acls = true
  restrict_public_buckets = true
}
```