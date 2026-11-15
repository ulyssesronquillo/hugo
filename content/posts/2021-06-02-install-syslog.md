---
title: 'install syslog'
author: ulysses

date: 2021-06-02
slug: install-syslog
draft: false
---

How to install syslog-np on Centos 7.

```
cd /tmp
wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum -y reinstall ./epel-release-latest-7.noarch.rpm
chattr +i /etc/yum.repos.d/epel*
yum -y install syslog-ng
```

Enable syslog-np. Disable rsyslog.

```
systemctl enable syslog-ng
systemctl start syslog-ng
yum -y erase rsyslog
```