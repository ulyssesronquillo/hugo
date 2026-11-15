---
title: 'list of encrypted volumes'
author: ulysses

date: 2019-03-18
slug: list-of-encrypted-volumes
draft: false
---

Here’s the AWS CLI to get a list of encrypted or unencrypted volumes.

```
# list of encrypted volumes
aws ec2 describe-volumes \
--filters Name=encrypted,Values=true \
--region us-east-1 --profile default \
--query "Volumes[*].{ID:VolumeId}" --output text
# list of unencrypted volumes
aws ec2 describe-volumes \
--filters Name=encrypted,Values=false \
--region us-east-1 --profile default \
--query "Volumes[*].{ID:VolumeId}" --output text
# count the list of encrypted volumes. use wc -l to get a count.
aws ec2 describe-volumes \
--filters Name=encrypted,Values=true \
--region us-east-1 --profile default \
--query "Volumes[*].{ID:VolumeId}" --output text | wc -l
```