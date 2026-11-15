---
title: 'install adoptopenjdk'
author: ulysses

date: 2021-10-28
slug: install-adoptopenjdk
draft: false
---

OpenJDK is an open-source implementation of the Java.

How to install AdoptOpenJDK.

TAR

```
cd /usr/java
wget --no-check-certificate https://bit.ly/3jKm3KZ
tar xzf OpenJDK8U-jdk_x64_linux_hotspot_8u312b07.tar.gz
export PATH=$PWD/jdk8u312-b07/bin:$PATH
java -version
```

RPM

```
cat  /etc/yum.repos.d/adoptopenjdk.repo
[AdoptOpenJDK]
name=AdoptOpenJDK
baseurl=http://adoptopenjdk.jfrog.io/adoptopenjdk/rpm/centos/$releasever/$basearch
enabled=1
gpgcheck=1
gpgkey=https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public
EOF
```

```
yum install adoptopenjdk-8-openj9
```