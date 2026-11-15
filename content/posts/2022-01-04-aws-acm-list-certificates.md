---
title: 'aws acm list certificates'
author: ulysses

date: 2022-01-04
slug: aws-acm-list-certificates
draft: false
---

How to list SSL certificates in AWS Certificate Manager.

```
aws acm list-certificates
```

Result

```
{
    "CertificateSummaryList": [
        {
            "CertificateArn": "arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "DomainName": "mydomain.com"
        }
    ]
}
```

Describe details about the certificate.

```
aws acm describe-certificate \
--certificate-arn arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx \
--region us-east-1 \
--profile my-profile
```