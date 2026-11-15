---
author: ulysses
title: 'timestamp timezone conversion'
date: 2024-02-24
slug: timestamp-timezone-conversion
draft: false
---

Here's a function that will convert a timestamp from one timezone to another, in this case from UTC to ET timezone.

Get a list of snapshots

```
list_snapshots() {
    volume_name="$1"
    snapshots=$(gcloud compute snapshots list --filter="sourceDisk=$volume_name" --format="value(name,creationTimestamp.date('%s'))")
    while read -r snapshot; do
        snapshot_name=$(echo "$snapshot" | cut -d' ' -f1)
        creation_timestamp=$(echo "$snapshot" | cut -d' ' -f2)
        et_creation_timestamp=$(convert_to_et "$creation_timestamp")
        echo "Snapshot: $snapshot_name, Creation Time (ET): $et_creation_timestamp"
    done <<< "$snapshots"
}
```

The function to convert to ET timezone.

```
convert_to_et() {
    timestamp="$1"
    et_timestamp=$(date --date="@${timestamp}" +"%Y-%m-%d %H:%M:%S %Z" -u)
    echo "$et_timestamp"
}
```

Finally, call the function.

```
volume_name="$1"
list_snapshots "$volume_name"
```
