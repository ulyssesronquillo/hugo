---
title: 'aws cli lightsail'
author: ulysses

date: 2019-05-19
slug: aws-cli-lightsail
draft: false
---

Get instance details

```
aws lightsail get-instance --instance-name your-server
```

Get instance state

```
aws lightsail get-instance-state --instance-name your-server
```

Create a snapshot

```
aws lightsail create-instance-snapshot \
--instance-snapshot-name your-server-new-snapshot-201905192200 \
--instance-name your-server
```

Create disk from snapshot

```
aws lightsail create-disk-from-snapshot \
--disk-name your-server-new-boot-disk \
--disk-name your-server-new-snapshot-201905192200 \
--availability-zone us-east-1a
--size-in-gb 50
```

Attach Disk

```
aws lightsail attach-disk \
--disk-name your-server-new-boot-disk \
--instance-name your-server \
--disk-path /dev/sda1
```

Create instance from snapshot

```
aws lightsail create-instance-snapshot \
--instance-snaphot-name your-server-new-snapshot-201905192200
--instance-name your-server
```

Attach Static IP Address

```
aws lightsail attach-static-ip \
--static-ip-name your-ip-name \
--instance-name your-server
```