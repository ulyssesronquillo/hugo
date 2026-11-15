---
title: 'create local yum repo'
author: ulysses

date: 2021-11-07
slug: create-local-yum-repo
draft: false
---

Here’s how to create a local yum repo.

Install Apache.

```
sudo yum install httpd
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

Install the repo packages.

```
sudo yum install createrepo yum-utils
```

Create repo directories.

```
sudo mkdir /var/www/html/{baseos,extras,appstream,epel}
```

Sync the repos.

```
sudo yum reposync -p=/var/www/html --repoid=baseos --download-metadata
sudo yum reposync -p=/var/www/html --repoid=extras --download-metadata
sudo yum reposync -p=/var/www/html --repoid=appstream --download-metadata
sudo yum reposync -p=/var/www/html --repoid=epel --download-metadata
```

Create a new repo.

```
sudo createrepo /var/www/html/
```

Setup a local repo.

```
sudo nano /etc/yum.repos.d/local.repo
```

Contents of local.repo.

```
local-base]
name=Yum Local Base
baseurl=http://10.10.0.20:80/base
enabled=1
gpgcheck=0
[local-extras]
name=Yum Local Extras
baseurl=http://10.10.0.20:80/extras
enabled=1
gpgcheck=0
[local-appstream]
name=Yum Local Appstream
baseurl=http://10.10.0.20:80/appstream
enabled=1
gpgcheck=0
[local-epel]
name=Yum Local Epel
baseurl=http://10.10.0.20:80/epel
enabled=1
gpgcheck=0
```

Confirm new repo is in the repolist.

```
sudo yum repolist
```