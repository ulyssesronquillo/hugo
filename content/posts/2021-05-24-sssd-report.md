---
title: 'sssd report'
author: ulysses

date: 2021-05-24
slug: sssd-report
draft: false
---

Generate a SSSD report.

```
#!/bin/bash
log="log"
> $log
sep () { echo "--------------------------------" >> $log; }
sep
echo "SSSD Status" >> $log
sep
systemctl status sssd >> $log
sep
echo "Contents of /etc/resolv.conf" >> $log
sep
cat /etc/resolv.conf >> $log
sep
echo "Contents of /etc/sssd/sssd.conf" >> $log
sep
cat /etc/sssd/sssd.conf >> $log
sep
echo "Versions of /etc/resolv.conf" >> $log
sep
ls -l /etc/resolv.conf* >> $log
sep
echo "Versions of /etc/sssd/sssd.conf" >> $log
sep
ls -l /etc/sssd/sssd.conf* >> $log
sep
echo "Contents of /var/log/sssd-rollout.log" >> $log
sep
cat /var/log/sssd-rollout.log >> $log
sep
echo "Contents of /var/log/sssd-rollout3.log" >> $log
sep
cat /var/log/sssd-rollout3.log >> $log
sep
```