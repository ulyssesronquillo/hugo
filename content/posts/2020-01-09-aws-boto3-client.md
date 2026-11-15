---
title: 'aws boto3 client'
author: ulysses

date: 2020-01-09
slug: aws-boto3-client
draft: false
---

Boto is the Amazon Web Services (AWS) SDK for Python. It enables Python developers to create, configure, and manage AWS services, such as EC2 and S3. Boto provides an easy to use, object-oriented API, as well as low-level access to AWS services.

Here’s a quick example how to query for AWS resources.

```
import logging
import boto3
from botocore.exceptions import ClientError

# set aws profile
session = boto3.Session(profile_name="default")

# get buckets
s3 = session.client('s3')
results = s3.list_buckets()

# display buckets
print('Existing buckets:')
for key in results['Buckets']:
    print(f'{key["Name"]}')

# get ec2 instances. set region.
ec2 = session.client('ec2', region_name='us-east-1')
results = ec2.describe_instances()

# display instances
for key in results["Reservations"]:
      for instance in key["Instances"]:
           instance_id = instance["InstanceId"]
           instance_type = instance["InstanceType"]
           availability_zone = instance["Placement"]["AvailabilityZone"]
           print(instance_id + "\t" + instance_type + "\t" + availability_zone)

# get list of users
client = session.client('iam')
results = client.list_users()

# display list of users
for key in results['Users']:
    print (key['UserName'])
```