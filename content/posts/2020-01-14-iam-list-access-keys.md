---
title: 'iam list access keys'
author: ulysses

date: 2020-01-14
slug: iam-list-access-keys
draft: false
---

Here’s how to list all the access keys in AWS via Python.

```
import logging
import boto3
from botocore.exceptions import ClientError

# set aws profile
session = boto3.Session(profile_name="default")

# get list of users

iam = session.client('iam')
users = iam.list_users()

# display results
print("{0:
```