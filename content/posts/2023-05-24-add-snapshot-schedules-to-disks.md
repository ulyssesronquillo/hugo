---
title: 'add snapshot schedules to disks'
author: ulysses

date: 2023-05-24
slug: add-snapshot-schedules-to-disks
draft: false
---

How to add Snapshot Schedules to disks in Terraform. Add this to your existing VM.

```
resource "google_compute_disk_resource_policy_attachment" "hourly_attachment" {
  name = "hourly-snapshots"
  disk = google_compute_instance.test.name
  zone = "us-central1-c"
}

resource "google_compute_disk_resource_policy_attachment" "daily_attachment" {
  name = "daily-snapshots"
  disk = google_compute_instance.test.name
  zone = "us-central1-c"
}
```