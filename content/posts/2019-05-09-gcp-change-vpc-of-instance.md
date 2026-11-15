---
title: 'gcp change vpc of instance'
author: ulysses

date: 2019-05-09
slug: gcp-change-vpc-of-instance
draft: false
---

The following are steps on how to change the network of an instance from one VPC to another. This is assuming you want to keep the same server name, but will need to make a network change. Unfortunately, changing networks will require creating a new instance. The following are the steps to make that change.

1. Keep track of all the disks.
2. Keep all disks including boot.
3. Stop the instance.
4. Create an image of the boot drive. Wait for it to complete.
5. Create a similar instance, but do not execute.
6. Make the network changes. Save the GCloud CLI command.
7. Delete the instance.
8. Run the saved command from step 4. This creates a new instance.
9. Stop the instance.
10. Detach the boot disk.
11. Attach all the other disks.
12. Boot the instance.