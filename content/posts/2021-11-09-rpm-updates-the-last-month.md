---
title: 'rpm updates the last month'
author: ulysses

date: 2021-11-09
slug: rpm-updates-the-last-month
draft: false
---

Here’s the software packages updated the last month.

```
rpm -qa --last | grep -w "$(date --date='1 month ago' +'%b %Y')"
```

Result

```
python-perf-3.10.0-1160.42.2.el7.x86_64       Mon 04 Oct 2021 02:16:16 AM UTC
openldap-2.4.44-24.el7_9.x86_64               Mon 04 Oct 2021 02:16:12 AM UTC
kpartx-0.4.9-135.el7_9.x86_64                 Mon 04 Oct 2021 02:16:09 AM UTC
kernel-tools-libs-3.10.0-1160.42.2.el7.x86_64 Mon 04 Oct 2021 02:16:05 AM UTC
kernel-tools-3.10.0-1160.42.2.el7.x86_64      Mon 04 Oct 2021 02:16:05 AM UTC
kernel-3.10.0-1160.42.2.el7.x86_64            Mon 04 Oct 2021 02:14:41 AM UTC
virt-what-1.18-4.el7_9.1.x86_64               Mon 04 Oct 2021 01:03:22 AM UTC
bind-export-libs-9.11.4-26.P2.el7_9.7.x86_64  Mon 04 Oct 2021 01:03:22 AM UTC
# ... truncated output
```