---
title: 'vintela troubleshooting'
author: ulysses

date: 2021-01-06
slug: vintela-troubleshooting
draft: false
---

Vintela is a utility for allowing AD users to login to Linux. Here are some basic troubleshooting tips.

```
#check version
vastool -v
# check status
vastool status
# start stop script
/etc/init.d/vasd start/stop/restart
# check user access
vastool user checkaccess username
# list users
vastool list users
# flush cache
vastool flush
# unjoin domain 
vastool unjoin -f -l
# join domain
vastool -u username@domain.com -w password join -f -c OU=Linux,OU=linux,OU=Servers,DC=domain.com,DC=net domain.com
```

Important files.

```
/etc/opt/quest/vas/host.keytab      Encrypted host key
/etc/opt/quest/vas/group-override   Maps accounts to groups
/etc/opt/quest/vas/users.allow      Lists groups that are granted access to the server
/etc/opt/quest/vas/xjoin.keytab     File used to join server to domain
/etc/opt/quest/vas/vas.conf         Primary VAS configuration file
/etc/opt/quest/vas/user-override    Allows you to override specific user settings
```