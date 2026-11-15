---
title: 'adding domains in certbot'
author: ulysses

date: 2021-01-25
slug: adding-domains-in-certbot
draft: false
---

You can register multiple domains to a single SSL certificate. This is particularly useful if you are hosting multiple domains on one server. This command adds more domains to your existing certificate.

```
certbot --expand -d existing.com -d newdomain1.com -d newdomain2.com
```

Check if the domains were added.

```
certbot certificates
```

Certbot certificates are valid for 90 days, but they automatically renew themselves if expiration is less than 30 days. If you need to renew manually for some odd reason, you can run this command. You can also perform a dry-run before renewing.

```
certbot renew
certbot renew --dry-run
```