---
title: 'aws efs userdata'
author: ulysses

date: 2018-12-25
slug: aws-efs-userdata
draft: false
---

If you want to auto mount the EFS volumes when the instance is created, add the following script to userdata:

```
#cloud-config
repo_upgrade: all

packages:
- amazon-efs-utils

runcmd:
- file_system_id_01=fs-12345678
- file_system_id_02=fs-34593405
- efs_directory_01=/mnt/efs
- efs_directory_02=/mnt/efs2

- mkdir -p ${efs_directory_01}
- mkdir -p ${efs_directory_02}

- echo "${file_system_id_01}:/ ${efs_directory_01} efs tls,_netdev" >> /etc/fstab
- echo "${file_system_id_02}:/ ${efs_directory_02} efs tls,_netdev" >> /etc/fstab

- mount -a -t efs defaults
```

Just add more if you have more mounts.