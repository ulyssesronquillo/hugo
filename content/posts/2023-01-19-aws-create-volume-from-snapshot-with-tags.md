---
title: 'aws create volume from snapshot with tags'
author: ulysses

date: 2023-01-19
slug: aws-create-volume-from-snapshot-with-tags
draft: false
---

Here’s another script that creates a volume from a snapshot, but also add the tags.

```
#!/bin/bash
read -p "server     : " server
read -p "volumeId   : " volume
read -p "snapshotId : " snapshot
read -p "region     : " region
read -p "zone       : " zone
read -p "profile    : " profile
# get tags
tags1=$(aws ec2 describe-volumes --volume-ids $volume --query 'Volumes[].Tags[]' --region $region --profile $profile)
# remove quotes
tags2=$(echo "$tags1" | tr -d '"')
# remove spaces
tags3=$(echo $tags2 | sed 's/ //g')
# replace : with =
tags4=$(echo $tags3 | sed 's/:/=/g')
# if empty value replace with quotes
tags5=$(echo $tags4 | sed 's/Value=}/Value=""}/g')
# create volume
aws ec2 create-volume \
--availability-zone $zone \
--encrypted \
--iops 3000 \
--volume-type gp3 \
--snapshot-id $snapshot \
--tag-specifications 'ResourceType=volume,Tags='$tags5'' \
--region $region \
--profile $profile
```