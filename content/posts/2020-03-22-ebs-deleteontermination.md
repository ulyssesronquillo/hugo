---
title: 'ebs deleteontermination'
author: ulysses

date: 2020-03-22
slug: ebs-deleteontermination
draft: false
---

Here’s how to set the DeleteOnTermination setting on EBS volumes. The DeleteOnTermination flag determines if an EBS volume will be kept or deleted when an EC2 instance is terminated. The DeleteOnTermination setting can be set during EC2 instance creation, or it can be applied to an existing or a running EC2 instance. The settings can be placed in a JSON file and loaded using –block-device-mappings option upon creation.

During creation.

```
aws ec2 run-instances \
--count 1 \
--region us-east-2 \
--key-name tfc-ohio \
--image-id ami-xxxxxxxx \
--instance-type t2.large \
--subnet-id subnet-xxxxxxx \
--private-ip-address 10.0.4.100 \
--iam-instance-profile Name=machinerole \
--security-group-ids sg-xxxxxxxxxxxxx \
--block-device-mappings file://mapping.json
```

Contents of mapping.json

```
[
  {
    "DeviceName": "/dev/sda1",
    "Ebs": {
      "DeleteOnTermination": true,
      "VolumeSize": 30
      "VolumeType": "gp2"
    }
  }
]
```

Device name is /dev/sda1. Termination is set to true. Volume size is 30GB and EBS type is gp2.

Modifying an existing EC2 instance.

```
aws ec2 modify-instance-attribute \
--instance-id i-xxxxxxxxxxxxx \
--block-device-mappings file://mapping.json
```

Here’s the mapping.json file.

```
[
  {
    "DeviceName": "/dev/sda1",
    "Ebs": {
      "DeleteOnTermination": false,
    }
  }
]
```

Obviously, you can’t change Volume size and type to an existing EBS volume, but you can flip the DeleteOnTermination flag and vice versa.