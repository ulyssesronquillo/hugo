---
title: 'migrate gcp vm to another network'
author: ulysses

date: 2019-09-10
slug: migrate-gcp-vm-to-another-network
draft: false
---

Here are the steps how to migrate a GCP VM from one network to another. It involves recreating the instance in that network.

1. Find the VM. Click the ‘Create Similar’ button.
2. Select the new network. Save Network. Everything else should stay the same.
3. Don’t click Create, but get the ‘Create Similar’ command line script only. Click Cancel after.
4. Make sure to edit the hostname. GCP appends a ‘-1’ at the end of hostname.
5. Edit VM to keep all disks. Delete VM. Make sure to preserve boot drive.
6. Run the ‘Create Similar’ command line script you capture to create new VM in the new network.
7. The new VM will be based on golden image.
8. Stop VM. Swap new disks with old disks.
9. Start VM.
10. Done.