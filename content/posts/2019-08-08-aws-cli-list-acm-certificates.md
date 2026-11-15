---
title: 'aws cli list acm certificates'
author: ulysses

date: 2019-08-08
slug: aws-cli-list-acm-certificates
draft: false
---

If you’ve imported or created a SSL certificate via AWS Certificate Manager, here’s the CLI to display a list of certificates.

```
aws acm list-certificates
```

Once you have the arn, you can describe certificate. Get the arn from the output above.

```
aws acm describe-certificate --certificate-arn arn-xxxxxxxxxxxxxxxxxx
```