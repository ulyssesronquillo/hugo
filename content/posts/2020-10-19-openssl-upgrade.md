---
title: 'openssl upgrade'
author: ulysses

date: 2020-10-19
slug: openssl-upgrade
draft: false
---

Here’s how to upgrade to OpenSSL 1.1 on Redhat/Centos.

```
# check
openssl version
yum info openssl
# download and install
cd /usr/local/src
wget https://www.openssl.org/source/openssl-1.0.2-latest.tar.gz
tar -zxf openssl-1.0.2-latest.tar.gz
# compile
cd openssl-1.0.2a
./config
make
make test
make install
# update softlink
mv /usr/bin/openssl /root/
ln -s /usr/local/ssl/bin/openssl /usr/bin/openssl
# verify new version
openssl version
```