---
title: 'encrypt volume via terraform'
author: ulysses

date: 2019-04-09
slug: encrypt-volume-via-terraform
draft: false
---

Here’s the Terraform script to encrypt an unencrypted volume. It creates a snapshot, encrypts a snapshot, and encrypts the volume.

```
#
# Set Variables
#
variable "volume" {
  description = "The Volume to encrypt: vol-12345678901234567"
}
variable "region" {
  description = "The Region: us-east-2"
}
variable "az" {
  description = "The AZ: us-east-2a"
}

#
# Set Credentials
#
provider "aws" {
	access_key = "put-your-access-key-here"
	secret_key = "put-your-secret-key-here"
	region = "${var.region}"
}

/*
#
# Create Unencrypted Volume
#
resource "aws_ebs_volume" "unencrypted_volume" {
  availability_zone = "${var.az}"
  size              = 10
  tags = {
    Name = "Unencrypted_Volume"
  }
}
*/

#
# Create Unencrypted Snapshot
#
resource "aws_ebs_snapshot" "unencrypted_snapshot" {
  #volume_id = "${aws_ebs_volume.unencrypted_volume.id}"
  volume_id = "${var.volume}"
  tags = {
    Name = "Unencrypted_Snapshot"
  }
}

#
# Create Encrypted Snapshot
#
resource "aws_ebs_snapshot_copy" "encrypted_snapshot" {
  source_snapshot_id = "${aws_ebs_snapshot.unencrypted_snapshot.id}"
  source_region      = "${var.region}"
  encrypted = true
  tags = {
    Name = "Encrypted_Snapshot"
  }
}

#
# Created Encrypted Volume
#
resource "aws_ebs_volume" "encrypted_volume" {
  availability_zone = "${var.az}"
  snapshot_id = "${aws_ebs_snapshot_copy.encrypted_snapshot.id}"
  tags = {
    Name = "Encrypted_Volume"
  }
}
```