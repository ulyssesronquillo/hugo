---
title: 'unbound logs'
author: ulysses

date: 2023-05-24
slug: unbound-logs
draft: false
---

How to enable unbound logs.

Add these line in /etc/unbound/unbound.conf.

```
chroot: ""
logfile: /var/log/unbound.log
verbosity: 4
log-queries: yes
```

Create the log file and set permissions.

```
touch /var/log/unbound.log
chown unbound:unbound /var/log/unbound.log
```

Restart the unbound service.

```
systemctl restart unbound
```

Check status.

```
systemctl status unbound
```

Finally, check the logs.

```
tail -f /var/log/unbound.log
```