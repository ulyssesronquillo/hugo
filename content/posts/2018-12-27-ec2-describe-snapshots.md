---
title: 'ec2 describe snapshots'
author: ulysses

date: 2018-12-27
slug: ec2-describe-snapshots
draft: false
---

If you have a ton of snapshots, they tend to be difficult to find within the AWS console. Although AWS has optimized the snapshot view, it’s still in beta. Filtering a volume id is still a problem. It might be faster just to use the AWS CLI to display snapshot information. Here’s an example of how to display snapshots given a certain volume id.

```
aws ec2 describe-snapshots \
--filters Name=volume-id,Values=vol-xxxxxxxxxxxxxx \
--query "Snapshots[*].{ID:SnapshotId,Time:StartTime,Progress:Progress}" \
--profile default
```

The result is something like this.

```
{
        "Progress": "99%",
        "ID": "snap-xxxxxxxxxxxxxxx",
        "Time": "2018-12-25T10:19:51.385Z"
    },
    {
        "Progress": "99%",
        "ID": "snap-xxxxxxxxxxxxxxx",
        "Time": "2018-12-24T09:35:09.357Z"
    }
```