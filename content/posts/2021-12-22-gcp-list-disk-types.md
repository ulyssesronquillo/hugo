---
title: 'gcp list disk types'
author: ulysses

date: 2021-12-22
slug: gcp-list-disk-types
draft: false
---

To list all disk types available in your project in all regions. Result is truncated.

```
$ gcloud compute disk-types list
NAME         ZONE                       VALID_DISK_SIZES
pd-balanced                             10GB-65536GB
pd-ssd                                  10GB-65536GB
pd-standard                             200GB-65536GB
pd-balanced                             10GB-65536GB
...
```

To list a specific region, use the filter option.

```
$ gcloud compute disk-types list --filter="zone~'us-central1'"
NAME         ZONE           VALID_DISK_SIZES
pd-balanced  us-central1-a  10GB-65536GB
pd-extreme   us-central1-a  500GB-65536GB
pd-ssd       us-central1-a  10GB-65536GB
pd-standard  us-central1-a  10GB-65536GB
pd-balanced  us-central1-b  10GB-65536GB
pd-extreme   us-central1-b  500GB-65536GB
pd-ssd       us-central1-b  10GB-65536GB
pd-standard  us-central1-b  10GB-65536GB
pd-balanced  us-central1-c  10GB-65536GB
pd-extreme   us-central1-c  500GB-65536GB
pd-ssd       us-central1-c  10GB-65536GB
pd-standard  us-central1-c  10GB-65536GB
pd-balanced  us-central1-f  10GB-65536GB
pd-extreme   us-central1-f  500GB-65536GB
pd-ssd       us-central1-f  10GB-65536GB
pd-standard  us-central1-f  10GB-65536GB
pd-balanced  us-central1-d  10GB-65536GB
pd-extreme   us-central1-d  500GB-65536GB
pd-ssd       us-central1-d  10GB-65536GB
pd-standard  us-central1-d  10GB-65536GB
```

To a list a specific region and local SSDs only.

```
gcloud compute disk-types list --filter="zone~'us-central1' AND name~'local-'"
NAME       ZONE           VALID_DISK_SIZES
local-ssd  us-central1-a  375GB-375GB
local-ssd  us-central1-b  375GB-375GB
local-ssd  us-central1-c  375GB-375GB
local-ssd  us-central1-f  375GB-375GB
local-ssd  us-central1-d  375GB-375GB
```