---
title: 'aws cli iam create user'
author: ulysses

date: 2019-07-22
slug: aws-cli-iam-create-user
draft: false
---

How to create an IAM user via AWS CLI.

```
aws iam create-user --user-name john.doe \
--tags Key='key1',Value='value1', Key='key2',Value='value2' \
--profile your-profile
```

To add keys.

```
aws iam create-access-key \
--user-name username \
--profile your-profile
```