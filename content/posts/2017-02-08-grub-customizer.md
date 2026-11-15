---
title: 'grub customizer'
author: ulysses

date: 2017-02-08
slug: grub-customizer
draft: false
---

Grub is a menu program that allows Linux users the ability to choose from a multi-boot system. The original Grub program allowed administrators the ability to edit the menu listing from the command line. Sadly, when Grub 2 was implemented, editing files no longer had the same effect. The files are being overwritten by the system. Any changes to the menu listing file is discarded.

What’s the fix?

One of the easiest way customize the Grub 2 menu listing is to use an application called Grub Customizer.

To install, perform the following commands:

```
$ sudo add-apt-repository ppa:danielrichter2007/grub-customizer
$ sudo apt-get update
$ sudo apt-get install grub-customizer
```

Once installed, access the program from the menu under Administration (Linux Mint 18).

Remove the entries you don’t want. Rename the entries to something meaningful to you.