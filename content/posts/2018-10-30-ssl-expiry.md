---
title: 'ssl expiry'
author: ulysses

date: 2018-10-30
slug: ssl-expiry
draft: false
---

It’s not always clear how to find out when your SSL certificate is expiring. Openssl should be able to tell you.

```
$ openssl x509 -enddate -noout -in certificate.crt
```