---
title: 'wiki ssl certificate location'
author: ulysses

date: 2021-11-12
slug: wiki-ssl-certificate-location
draft: false
---

Here’s where the Wiki keeps its SSL certificate keys.

```
/etc/pki/tls/certs/yourdomain.crt
/etc/pki/tls/private/yourdomain.key
```

In some cases, SSL needs to be converted so it doesn’t prompt you for a password if you restart Apache.

Conversion

```
openssl rsa -in /etc/pki/tls/private/yourdomain.key.new -out /etc/pki/tls/private/yourdomain.key.new_no_pass
```