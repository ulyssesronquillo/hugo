---
title: 'aws cli using query'
author: ulysses

date: 2020-11-11
slug: aws-cli-using-query
draft: false
---

Instead of using AWS and JQ to get the snapshot names, you can do it with a single command using –query.

Here are the previous commands.

```
/usr/bin/aws lightsail get-instance-snapshots --region us-east-1 --profile default > $snaps
cat $snaps | jq -r '.instanceSnapshots[] | .name' > $names
```

Using query.

```
aws lightsail get-instance-snapshots \
--query 'instanceSnapshots[*].[name]' \
--region us-east-1 \
--profile default \
--output text > $names
```