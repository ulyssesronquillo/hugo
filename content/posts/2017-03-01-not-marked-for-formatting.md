---
title: 'not marked for formatting'
author: ulysses

date: 2017-03-01
slug: not-marked-for-formatting
draft: false
---

I have a Linux box with a 1TB drive. I divided it into 4 different partitions at 250GB each. It’s currently running Linux Mint, Gitlab, Nextcloud and the Unifi Cloud Controller on each partition. Obviously, I can’t run all 4 partitions at the same time. I have to choose one from a selection in the Grub, a multi-boot loader. It would have been easier to run Virtualbox on just one Linux install, but it’s older CPU. I don’t think it could handle multiple OS running at the same time.

Unfortunately, one of the partitions got corrupted. I tried running the utility called badblocks to figure out if there are any bad sectors on the drive that can be marked bad, but the test result turned out to be surprisingly good. There were absolutely no errors and no bad blocks. Next, I tried using the recovery process, but that didn’t work either. It seems the only way to fix the problem was to reinstall Linux. A bummer.

During the install, I ran into the problem with the partition not being properly marked for formatting. It seems the only way to get around that issue was to delete the partition and to repartition it. Nevertheless, it would have been an interesting dilemma if I had any important data on that partition. It’s a good thing that I didn’t. So, if you ever get into a problem where it says “your partition is not marked for formatting”, you may have to go through the process of deleting the partition and then recreating one, in order to proceed with a fresh install.