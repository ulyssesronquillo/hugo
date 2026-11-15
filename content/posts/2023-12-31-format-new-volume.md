---
author: ulysses
title: 'format new volume'
date: 2023-12-31
slug: format-new-volume
draft: false
---

I recently bought a 2TB NVME SSD drive which I plan to install on my Linux Mint desktop. I have been taking a ton of pictures lately with my old Nikon D700 DSLR camera and I can use the extra space. Since the new drive is unformatted, here were the steps that I took to get it working on my desktop. This how-to assumes that I have installed the new NVME drive on your motherboard successfully.

The first thing to do is to find out the device name. It shows up as a 1.8TB disk on my desktop.

```
lsblk
nvme0n1 259:0    0   1.8T  0 disk
```

Check if it's formatted. It should be empty. If not, it will display the file system type.

```
sudo file -s /dev/nvme0n1 
```

If empty.

```
/dev/nvme0n1: data
```

If formatted with XFS.

```
/dev/nvme0n1: SGI XFS filesystem data (blksz 4096, inosz 512, v2 dirs)
```

Since it's empty, let's format the drive. I will use XFS as the file system.

```
mkfs -t xfs /dev/nvme0n1 
```

Let's mount the drive after formatting. I will use the Nikon directory in my home directory as the mount volume.

```
mkdir ~/Nikon
sudo mount /dev/nvme0n1 /home/ulysses/Nikon
```

Let's unmount it temporarily.

```
sudo umount /home/ulysses/Nikon
```

Next, I will add an entry to the /etc/fstab to make the drive mount permanent after each reboot. Get the UUID of the new drive using the blkid command.

```
sudo blkid 
```

Now edit the /etc/fstab file to add the new volume entry.

```
vi /etc/fstab
```

The entry will look similar to this. Enter the UUID by replacing the x's.

```
UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /home/ulysses/Nikon          xfs        defaults            0 0
```

Test it by mounting all.

```
sudo mount -a 
```

If there are no errors, mount was successful. You can check by running the df command.

```
df -Th
```

It should display something similar to below. I already have 5% data on the drive. 

```
/dev/nvme0n1        xfs        1.9T   83G  1.8T   5% /home/ulysses/Nikon
```

Since everything looks good, I can now safely reboot.

```
sudo shutdown -r 
```
