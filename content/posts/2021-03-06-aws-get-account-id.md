---
title: 'aws get account id'
author: ulysses

date: 2021-03-06
slug: aws-get-account-id
draft: false
---

Here’s a quick way to find the AWS Account ID via AWS CLI.

```
aws sts get-caller-identity --query Account --output text
```

Output is a 12 digit number (redacted)

```
xxxxxxxxxxxx
```

AWS Account ID is a 12 digit number unique to each AWS account. Occasionally, there are scripts and policies that need the ID of the account. The command above is one way of querying the account ID so they can be used for policies that need them.