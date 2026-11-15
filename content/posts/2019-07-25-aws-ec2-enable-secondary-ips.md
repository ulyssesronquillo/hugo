---
title: 'aws ec2 enable secondary ips'
author: ulysses

date: 2019-07-25
slug: aws-ec2-enable-secondary-ips
draft: false
---

Here’s how to enable secondary private IPs for AWS EC2 instances.

1. Add secondary private IPs to the instance. 
    - Editing the instance Networking &gt; Manage IP Addresses.
    - Add new private IP addresses.
    - Save.
2. Set the route configuration for each secondary IP address.
    - Config files are ifcfg-eth0:0, ifcfg-eth:0.1 and so on.
    - Test each interface or IP to see if they respond to ping.
    - /etc/sysconfig/network-scripts/

ifcfg-eth0:0

```
NM_CONTROLLED="no"
DEVICE="eth0:0"
ONBOOT="yes"
BOOTPROTO="static"
IPADDR="10.0.0.14"
NETMASK="255.255.255.255"
```

ifcfg-eth0:1

```
NM_CONTROLLED="no"
DEVICE="eth0:1"
ONBOOT="yes"
BOOTPROTO="static"
IPADDR="10.0.0.15"
NETMASK="255.255.255.255"
```