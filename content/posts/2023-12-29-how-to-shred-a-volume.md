---
author: ulysses
title: 'how to shred a volume'
date: 2023-12-29
slug: how-to-shred-a-volume
draft: false
---

If you have a disk drive, SSD or NVME storage device that need to be wiped clean, I recommend that you use the shred command.

In this example, I'm cleaning up the contents of my NVME device at /dev/nvme0n1.

```
sudo shred -v -n 1 --random-source=/dev/urandom -z /dev/nvme0n1
```

I'm using these options and their explanation.

- -v is verbose
- -n is the number of iterations. Mine is set to 1. You can increase it, but it can take hours.
- --random-source is set to /dev/urandom which is the kernel's random number generator.
- -z means everything gets overwritten by zeros.

Shred will make it nearly impossible to steal your data.
