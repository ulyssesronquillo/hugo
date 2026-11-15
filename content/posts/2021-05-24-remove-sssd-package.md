---
title: 'remove sssd package'
author: ulysses

date: 2021-05-24
slug: remove-sssd-package
draft: false
---

How to remove SSSD package.

```
#!/bin/bash
service sssd stop
chkconfig sssd off
rm -rf /var/lib/sss/db/*
rm -f /etc/sssd/sssd.conf
rm -f /etc/krb5.conf
rm -f /etc/krb5.keytab
yum remove -y adcli sssd authconfig pam_krb5 samba4-common realmd
```