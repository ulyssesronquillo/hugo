---
title: 'aws display iam certificates'
author: ulysses

date: 2020-01-22
slug: aws-display-iam-certificates
draft: false
---

SSL certificates were uploaded to IAM prior to Certificate Manager. Unfortunately, the certificates are not visible from the IAM console. There’s no way to view when a certificate is expiring. So, here’s how to display IAM certificates from the AWS CLI.

```
aws iam list-server-certificates
```