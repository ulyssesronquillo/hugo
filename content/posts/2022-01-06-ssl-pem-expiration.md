---
title: 'ssl pem expiration'
author: ulysses

date: 2022-01-06
slug: ssl-pem-expiration
draft: false
---

Find out when SSL expires from a PEM file.

```
$ openssl x509 -enddate -noout -in your.cert
notAfter=Jan  5 07:08:14 2032 GMT
```

notAfter date is returned.