---
author: ulysses
title: 'gcp create hyperdisks'
date: 2024-02-05
slug: gcp-create-hyperdisks
draft: false
---

GCP has new generation of disks for demanding and mission-critical applications. Hyperdisks is not available on all VMs, but they are usually available on large machine types. You create a Hyperdisk from scratch and attach it to an existing VM or convert a current disk by way of a snapshot. Here's the script to convert it an existing disk to Hyperdisk from a snapshot.

There are 3 types of Hyperdisks

1. Hyperdisk Balanced
2. Hyperdisk Extreme
3. Hyperdisk Throughput

Convert from snapshot.

```
gcloud compute disks create $disk \
  --source-snapshot="$snap" \
  --type="hyperdisk-extreme" \
  --zone="$zone" \
  --project="$project"
```

Or create a new one.

```
gcloud compute disks create $disk \
   --zone="$zone" \
   --size=100 \
   --type="hyperdisk-extreme" \
   --project="$project" 
```

IOPS and Throughput are optional values. You can let GCP decide the default or override it. 

```
   --provisioned-iops=IOPS_LIMIT
   --provisioned-throughput=THROUGHPUT_LIMIT
```
