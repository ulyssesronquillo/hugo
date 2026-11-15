---
title: 'chrony service'
author: ulysses

date: 2019-07-28
slug: chrony-service
draft: false
---

The chrony service actually does not change the time. The misconception is that the chrony service is setting the time given by the NTP server. This is not what’s happening. The chrony service is just telling the system clock to go faster or slower. This is the reason why sometimes even though the time is wrong and the NTP server is working, the time does not get corrected immediately. It takes a little while.