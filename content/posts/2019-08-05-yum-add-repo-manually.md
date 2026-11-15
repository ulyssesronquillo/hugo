---
title: 'yum add repo manually'
author: ulysses

date: 2019-08-05
slug: yum-add-repo-manually
draft: false
---

Add a yum repo manually by adding a configuration file in /etc/yum.repo.d/ directory.

```
cd /etc/yum.repos.d/
vi newrepo
```

Add the following.

```
[newrepo]
name=New Repo for RHEL/ CentOS $releasever - $basearch
baseurl=http://newrepo.domain.com/centos/$releasever/$basearch/
enabled=1
gpgcheck=1
gpgkey=http://newrepo.domain.com/RPM-GPG-KEY.txt
```

You may need to import the key.

```
rpm --import http://newrepo.domain.com/RPM-GPG-KEY.txt
```

Finally, test the new repo by running the following.

```
yum update -y
yum install new-package
```