---
author: ulysses
title: 'gcp vm list all snapshots'
date: 2023-12-19
slug: gcp-vm-list-all-snapshots
draft: false
---

Here's how to list all the snapshots for a particular VM in GCP.

```
#!/bin/bash

if [ "$#" -ne 3 ]
then
  echo "Usage: ./gcp-list-all-snapshots.sh project server policy"
  exit
fi

# Set the name of the snapshot schedule policy and the disk name to filter by
PROJECT=$1            # PROJECT="projectId"
SERVER=$2             # DISK_NAME="hostname"
POLICY=$3             # POLICY_NAME="hourly or daily"

disks=$(gcloud compute disks list --project $PROJECT --filter="name~$SERVER" --format="value(name)") 

for disk in $disks; do

  # List all snapshots created by the snapshot schedule policy
  gcloud compute snapshots list \
  --filter="sourceSnapshotSchedulePolicy ~ $POLICY AND sourceDisk~$disk$" \
  --format="table(sourceDisk.basename(),name,creationTimestamp,sourceSnapshotSchedulePolicy.basename())" \
  --sort-by "~creationTimestamp" \
  --project="$PROJECT"

done
```

The script requires three arguments: projectId, hostname and policy.
