---
title: 'ec2 delete snapshots'
author: ulysses

date: 2018-12-27
slug: ec2-delete-snapshots
draft: false
---

Here’s the AWS CLI command for deleting a snapshot.

```
aws ec2 delete-snapshot \
--snapshot-id snap-xxxxxxxxxxxxxxx \
--profile default
```