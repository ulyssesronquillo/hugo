---
title: 'aws create volume from snapshot'
author: ulysses

date: 2023-01-18
slug: aws-create-volume-from-snapshot
draft: false
---

Here’s a bash script that creates a volume from a snapshot in AWS.

```
#!/bin/bash
read -p "snapshotId : " snapshot
read -p "server     : " server
read -p "tag1       : " tag1
read -p "tag2       : " tag2
read -p "region     : " region
read -p "zone       : " zone
read -p "profile    : " profile
aws ec2 create-volume \
--availability-zone $zone \
--encrypted \
--iops 3000 \
--volume-type gp3 \
--snapshot-id $snapshot \
--tag-specifications "ResourceType=volume,Tags=[{Key=Name,Value="$server"},{Key=tag1,Value="$tag1"},{Key=tag2,Value="$tag2"}]" \
--region $region \
--profile $profile
```