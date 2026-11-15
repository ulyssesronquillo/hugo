---
title: 'check certificate expiration'
author: ulysses

date: 2021-10-20
slug: check-certificate-expiration
draft: false
---

Here’s the openssl command to find out if a cert is expired.

```
$ openssl s_client -connect yourdomain.com:443 -servername yourdomain.com 2> /dev/null | openssl x509 -noout -dates
```

Result

```
notBefore=Apr  9 00:00:00 2020 GMT
notAfter=Apr  9 23:59:59 2022 GMT
```