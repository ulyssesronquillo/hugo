---
title: 'create local repo in rocky linux 8'
author: ulysses

date: 2022-01-30
slug: create-local-repo-in-rocky-linux-8
draft: false
---

How to create a local repo in Rocky Linux 8.

Install nginx. Enable service.

```
dnf install nginx
systemctl enable nginx --now
systemctl status nginx
```

Create repo.

```
dnf repolist
dnf install createrepo yum-utils
mkdir /usr/share/nginx/html/repos
mkdir -p /usr/share/nginx/html/repos/{baseos,appstream}
```

Sync repos.

```
dnf reposync -g --delete -p /usr/share/nginx/html/repos/ --repoid=baseos --newest-only --download-metadata
dnf reposync -g --delete -p /usr/share/nginx/html/repos/ --repoid=appstream --newest-only --download-metadata
createrepo /usr/share/nginx/html/repos/baseos/
createrepo /usr/share/nginx/html/repos/appstream/
```

Create cron to sync repos daily. Create file called /etc/cron.daily/update-localrepos

```
#!/bin/bash
/bin/dnf reposync -g --delete -p /usr/share/nginx/html/repos/ --repoid=baseos --newest-only --download-metadata
/bin/dnf reposync -g --delete -p /usr/share/nginx/html/repos/ --repoid=appstream --newest-only --download-metadata
/usr/bin/createrepo /usr/share/nginx/html/repos/baseos/
/usr/bin/createrepo /usr/share/nginx/html/repos/appstream/
```

Create a file called /etc/nginx/conf.d/repos.conf.

```
server {
        listen   80;
        server_name  reposerver.example.com;
        root   /usr/share/nginx/html/repos;
	index index.html; 
	location / {
                autoindex on;
        }
}
```

Restart nginx.

```
systemctl restart nginx
```

Configure firewall and SELinux.

```
firewall-cmd --zone=public --permanent --add-service=http
firewall-cmd --reload
getenforce
chcon -Rt httpd_sys_content_t /usr/share/nginx/html/repos/
```

Move existing repos to /tmp.

```
mv /etc/yum.repos.d/*.repo /tmp/
```

Create a new repo called /etc/yum.repos.d/localrepo.repo

```
[localrepo-base]
name=RockyLinux Base
baseurl=http://reposerver.example.com/baseos/
gpgcheck=0
enabled=1
[localrepo-appstream]
name=RockyLinux Base
baseurl=http://reposerver.example.com/appstream/
gpgcheck=0
enabled=1
```

Clean cache and check repolist.

```
dnf clean all 
dnf repolist
```

Edit /etc/hosts and add reposerver.example.com. Add it to other hosts.

```
echo "10.10.10.10        reposerver.example.com     reposerver" >> /etc/hosts
```

Finally, run yum install against the local repo. Installing lvm in this example.

```
yum install lvm2
```