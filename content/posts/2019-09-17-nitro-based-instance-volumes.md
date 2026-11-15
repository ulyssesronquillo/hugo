---
title: 'nitro-based instance volumes'
author: ulysses

date: 2019-09-17
slug: nitro-based-instance-volumes
draft: false
---

AWS introduced Nitro-based instances which are modular. They are meant for high performance, high availability, and high security systems. Nitro building blocks provide direct access to high-speed local storage over a PCI interface and transparently encrypts all data using dedicated hardware. It also provides hardware-level isolation between storage devices and EC2 instances so that bare metal instances can benefit from local NVMe storage. The following are Nitro-based instances: A1, C5, C5d, C5n, I3en, M5, M5a, M5ad, M5d, p3dn.24xlarge, R5, R5a, R5ad, R5d, T3, T3a, and z1d. Bare metal: c5.metal, c5n.metal, i3.metal, i3en.metal, m5.metal, m5d.metal, r5.metal, r5d.metal, u-6tb1.metal, u-9tb1.metal, u-12tb1.metal, and z1d.metal.

Although Nitro-based instances looks like regular volumes (/dev/xvda) from the AWS Console, inside the operating system, they look (/dev/nvme6n1) completely different.

In AWS Console, the storage devices will look like this.

```
/dev/sda1
/dev/xvdb
/dev/xvdc
/dev/xvdd
/dev/xvde
/dev/xvdh
/dev/xvdf
/dev/xvdi
/dev/xvdg
/dev/xvdj
```

In the operating system, invoking df -h, results in this.

```
/dev/nvme0n1p2   30G  7.0G   24G  24% /
/dev/nvme4n1     50G   20G   31G  40% /vol1
/dev/nvme1n1     10G  753M  9.3G   8% /vol2
/dev/nvme8n1    500G   67G  433G  14% /backups
/dev/nvme2n1    400G   12G  388G   3% /vol3
/dev/nvme6n1    150G  150G  755M 100% /vol4
/dev/nvme7n1     10G   33M   10G   1% /vol5
/dev/nvme5n1     10G  553M  9.5G   6% /vol6
/dev/nvme9n1    100G   91G   10G  91% /vol7
```

The big question is, how can you tell which volume is associated with which. You’ll need nvme program to map out the volumes. Install nvme-cli first.

```
yum install nvme-cli
```

Then run the command below.

```
# run nvme
sudo nvme id-ctrl -v /dev/nvme6n1 | grep xv
# the result
0000: 2f 64 65 76 2f 73 64 6a 20 20 20 20 20 20 20 20 "/dev/xvdf..."
```