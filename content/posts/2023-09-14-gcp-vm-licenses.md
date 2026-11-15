---
title: 'gcp vm licenses'
author: ulysses

date: 2023-09-14
slug: gcp-vm-licenses
draft: false
---

Here’s the command to display VM OS licenses.

```
#!/bin/bash
ts=$(date +%Y%m%d-%H%M%S)
log="gcp-licenses-logs-$ts"
>$log
while read -r project; do
    echo "Project: $project" | tee -a $log
    gcloud compute instances list --project $project --format="table[no-heading](name,zone.basename())" > instances.list
    while read -r instance zone; do
        gcloud compute instances describe $instance \
        --project $project \
        --zone $zone \
        --format="table[no-heading](name,zone.basename(),disks[0].licenses[0].basename())" | tee -a $log
    done < instances.list
done < projectIds.list
```

It's going to go through a list of VM's in each project and display the name, zone and license information.
