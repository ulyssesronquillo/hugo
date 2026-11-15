---
title: 'aws certificate list'
author: ulysses

date: 2020-06-03
slug: aws-certificate-list
draft: false
---

Here’s how to get a list of certificates in AWS Certificate Manager.

```
aws acm list-certificates \
--profile default \
--region us-east-1 \
--output text \
--query 'CertificateSummaryList[*].{ARN:CertificateArn,Domain:DomainName}'
```