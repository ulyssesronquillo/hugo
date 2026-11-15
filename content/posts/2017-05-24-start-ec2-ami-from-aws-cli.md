---
title: 'start ec2 ami from aws cli'
author: ulysses

date: 2017-05-24
slug: start-ec2-ami-from-aws-cli
draft: false
---

Amazon Web Services has an API via a CLI (command line interface) which give users the ability to manage servers from a remote host. The AWS CLI must be installed and authenticated to AWS on the host computer. Once a user is logged in to AWS, they can perform certain management tasks such as starting and stopping EC2 instances.

**How to start EC2 instance from AWS CLI**

Requires an image id, instance count, instance type, key and security group.

```
aws ec2 run-instances --image-id ami-xxxxxxxx --count 1 --instance-type c4.2xlarge --key-name your-key  —security-group-ids sg-xxxxxxxx
```

**How to Associate an Elastic IP Address to an Instance**

Requires an instance id and Elastic IP address.

```
aws ec2 associate-address --instance-id i-xxxxxxxxxxxxxxxx --public-ip xxx.xxx.xxx.xxx
```

**How to Terminate an Instance**

Requires an instance id(s).

```
aws ec2 terminate-instances --instance-ids i-xxxxxxxxxxxxxxxx
```