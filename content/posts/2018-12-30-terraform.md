---
title: terraform
author: ulysses

date: 2018-12-30
slug: terraform
draft: false
---

Hashicorp has a product called [Terraform](https://learn.hashicorp.com/terraform/), which is a provisioning tool for the cloud. It works with most major providers like AWS, GCP, Azure and many more. Unlike [CloudFormation](https://aws.amazon.com/cloudformation/), [Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/) and [Deployment Manager](https://cloud.google.com/deployment-manager/docs/), Terraform will work with not just its own, but with many cloud providers. Here’s an example of how to provision a single instance to AWS, and assign an elastic IP to it. The cloud resources in the example were redacted. Placeholder values were placed instead for security purposes.

```
provider "aws" {
	access_key = "xxxxxxxx"
	secret_key = "xxxxxxxxxxxxxxxxxxxxxxxxxx"
	region = "us-east-2"
}

resource "aws_instance" "server1" {
	ami = "ami-xxxxxxxxxxxxxx"
	key_name = "tfc-ohio"
	instance_type = "c5.2xlarge"
	subnet_id = "subnet-xxxxxxxx"
	security_groups	= ["sg-xxxxxxxxxxxxxxx"]
	private_ip = "10.0.4.100"
	tags {
		Name = "Server One"
	}
}

resource "aws_eip_association" "server1-eip" {
  instance_id = "${aws_instance.server1.id}"
  allocation_id = "eipalloc-xxxxxxxx"
}
```

To provision an instance, just run:

```
terraform apply
```

When you are done, just run:

```
terraform destroy
```