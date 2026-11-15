---
title: 'convert pfx to pem format'
author: ulysses

date: 2019-04-03
slug: convert-pfx-to-pem-format
draft: false
---

SSL certificates comes in multiple formats. Some providers will hand you over certificates in PFX format which comes in a single file. If you need to import it to AWS Certificate Manager, you will need to convert it from PFX to PEM format. The following set of commands uses OpenSSL and pkcs12 to convert a SSL certificate from PFX to PEM format.

```
openssl pkcs12 -in cert.pfx -nocerts -out key.pem
openssl rsa -in key.pem -out server.key
openssl pkcs12 -in cert.pfx -clcerts -nokeys -out cert.pem
openssl pkcs12 -in cert.pfx -nodes -nokeys -out chain.pem
```

It result in 3 files.

- server.key is the private key
- cert.pem is the certificate
- cert.pem and chain.pem are the full chain.

Once you have them, you can the proceed to import it to ACM.

![](https://uly.me/wp-content/uploads/2019/01/cm.png)

SSL Certificate Import