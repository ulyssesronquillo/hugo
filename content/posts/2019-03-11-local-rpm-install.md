---
title: 'local rpm install'
author: ulysses

date: 2019-03-11
slug: local-rpm-install
draft: false
---

Steps for creating a local RPM package installation.

```
# download plugin
yum install yum-plugin-downloadonly
# download package and dependencies
yum install --downloadonly reiserfs
# download package and dependencies to a specific directory
yum install --downloadonly --downloaddir=/home/ec2-user package
# download multiple packages
yum install --downloadonly --downloaddir=/root/mypackages/ package1 package2
# finally install package
rpm -ivh -r /home/ec2-user package.rpm
```