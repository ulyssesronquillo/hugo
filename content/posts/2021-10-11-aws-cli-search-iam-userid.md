---
title: 'aws cli search iam userid'
author: ulysses

date: 2021-10-11
slug: aws-cli-search-iam-userid
draft: false
---

Here’s how to search for an IAM user in AWS by filtering their access key.

```
aws iam list-users --query 'Users[?UserId==`AIDAxxxxxxxxxxxxxxxxx`]' \
--profile your-profile
```

The results only returns one user with that UserID.

```
[
    {
        "Path": "/",
        "UserName": "your-username",
        "UserId": "AIDAxxxxxxxxxxxxxxxxx",
        "Arn": "arn:aws:iam::xxxxxxxxxxxx:user/sa-lucidchart",
        "CreateDate": "2019-04-15T15:53:18+00:00"
    }
]
```