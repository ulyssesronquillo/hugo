---
title: 'aws ec2 describe snapshots'
author: ulysses

date: 2020-05-07
slug: aws-ec2-describe-snapshots
draft: false
---

Here’s how to describe snapshots using query with tags.

```
aws ec2 describe-snapshots \
--owner-ids xxxxxxxxxxx \
--profile default \
--region us-east-2 \
--output text \
--query "Snapshots[*].[SnapshotId,Tags[?Key=='Name'].Value[] | [0]]"
```

Result.

```
snap-xxxxxxxxxxxxxxxxx	Server1
snap-xxxxxxxxxxxxxxxxx	Server2
```