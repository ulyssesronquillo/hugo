---
title: 'installing windows after linux'
author: ulysses

date: 2014-01-08
slug: installing-windows-after-linux
draft: false
---

Dual boot desktops makes sense. Most techies prefer it. There’s no need for an extra computer. It’s also less clutter on the desk. If you had to install two or more OS on a bare system, I suggest that you install Windows first, followed by Linux. Doing it the other way around, in installing Linux first and then Windows, is certainly doable, but you have to perform an extra step to fix Grub. Grub is the boot loader for Linux systems. Windows removes the Linux Grub entry from the MBR (Master Boot Record) after Windows is installed. This is a case of Microsoft not playing nice. Running a Linux recovery CD, to reinstate Grub in the MBR, does the trick.

So, here are the major steps in installing Windows after Linux.

1. Create a Windows partition in Linux using either a Disk Utility or GParted.
2. Install Windows on the new Windows partition.
3. Run the Recovery CD to restore Grub in the MBR.

The other option is to run Windows inside a Linux virtual machine. You will have lots of flexibility with this setup. You can have as many virtual machines running different OS. You can also have multiple OS running at the same time, as opposed to just one OS running on the system. There’s also another thing to consider. Systems that run in a virtual machine, tend to be not as fast as systems that run natively. It’s because virtual machines have to share resources with the host OS and other virtual machines that are running at the same time.

So, those are the tough choices when considering a dual boot OS. You have to figure out which OS to install first? Windows or Linux? Chances are, you may not have that luxury, since you already have an OS installed on your system. The other major option is to whether to run Windows in a virtual machine or using dual boot. Tough choices, but all very doable. It’s just a matter of preference.