---
title: 'top shift i'
author: ulysses

date: 2021-01-08
slug: top-shift-i
draft: false
---

When you run top on Linux with multiple processors, you can have processes with percentages higher than 100%. On a 4 core system, you can have a process that can run as high as 400%. To view it differently, press “shift i” while top is running. This will toggle the Irix mode to off. Pressing it again will turn it on. When the Irix mode is off, it will only show percentages divided by a total number of CPUs. This way, you get a true percentage of a process in a multiple core system.

[![](https://uly.me/wp-content/uploads/2021/01/top.png)](https://uly.me/wp-content/uploads/2021/01/top.png)

Pressing 1 interestingly shows the breakdown of all CPUs.