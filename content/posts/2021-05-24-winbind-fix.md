---
title: 'winbind fix'
author: ulysses

date: 2021-05-24
slug: winbind-fix
draft: false
---

Here’s the process to restore Winbind.

Restore old config.

```
cp /etc/sssd/sssd.conf-xxxxxxx /etc/sssd/sssd.conf
cp /etc/krb5.conf-xxxxxxx /etc/krb5.conf
```

Disable SSSD. Authconfig creates /etc/nswitch.conf.

```
authconfig --disablesssd --disablesssdauth --updateall
```

Start Winbind.

```
service winbind start; service smb start; service nmb start
```