---
author: ulysses
title: 'aws efs tls stunnel'
date: 2025-12-09
slug: aws-efs-tls-stunnel
draft: false
---
AWS EFS supports stunnel-based TLS encryption for NFS mounts.

Make sure distro has efs-utils installed.

```
sudo yum install -y amazon-efs-utils
# OR
sudo apt-get install -y amazon-efs-utils
```

nfs-utils will mount drives but it will not provide encryption.

```
sudo yum install nfs-utils
```

Standard mount with TLS

```
sudo mkdir -p /mnt/efs 
sudo mount -t efs -o tls fs-12345678:/ /mnt/efs 
```

Mount via /etc/fstab

```
fs-12345678:/ /mnt/efs efs _netdev,tls 0 0 
10.10.10.10:/ /mnt/efs efs _netdev,tls 0 0 
```

Mount automatically 

``` 
sudo mount -a
```

Check whether stunnel or efs-proxy is running

```
ps aux | grep -E "stunnel|efs-proxy"
```

aws-efs-utils in not avaiable on RedHat 6 & 7.