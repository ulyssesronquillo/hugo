---
title: 'mysql ssl connection'
author: ulysses

date: 2020-04-27
slug: mysql-ssl-connection
draft: false
---

The standard way to connect to MySQL is:

```
mysql -h hostname -u user -p
```

Here’s how to connect to MySQL with SSL encryption.

```
mysql -h hostname -u user -p \
--ssl-ca=server-ca.pem \
--ssl-cert=client-cert.pem \
--ssl-key=client-key.pem
```

Generate the SSL keys from the MySQL server. Download it to the client.