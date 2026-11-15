---
title: 'aws request domain renewal'
author: ulysses

date: 2021-09-17
slug: aws-request-domain-renewal
draft: false
---

Occassionally, AWS requires validation of your domain via email message. Here’s the command to send a request.

```
aws acm resend-validation-email \
--certificate-arn arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx \
--domain yourdomain.com \
--validation-domain yourdomain.com

aws acm resend-validation-email \
--certificate-arn arn:aws:acm:us-east-1:xxxxxxxxxxxx:certificate/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx \
--domain www.yourdomain.com \
--validation-domain yourdomain.com
```

You will need acm:ResendValidationEmail permission to run the command.