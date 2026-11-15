---
title: 'tomcat install'
author: ulysses

date: 2021-06-04
slug: tomcat-install
draft: false
---

Tomcat requires JRE.

```
wget jre-8uversion-linux-x64.tar.gz
# or
apt-get install default-jdk
```

Install Tomcat 8 on Linux.

```
wget https://mirrors.gigenet.com/apache/tomcat/tomcat-8/v8.5.66/bin/apache-tomcat-8.5.66.tar.gz
tar zxpvf apache-tomcat-8.5.66.tar.gz
cd /opt/tomcat/apache-tomcat-8.5.66/bin/
./startup.sh
```

Status|Start|Stop|Restart Tomcat.

```
systemctl status tomcat8
systemctl start tomcat8
systemctl stop tomcat8
systemctl restart tomcat8
```