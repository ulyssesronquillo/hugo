---
title: 'chrome bug with wordpress dashboard'
author: ulysses

date: 2015-09-09
slug: chrome-bug-with-wordpress-dashboard
draft: false
---

There’s a bug on Google Chrome with the latest WordPress Dashboard. The bug has been submitted to WordPress’ bug tracker. However, the [case is closed](https://core.trac.wordpress.org/ticket/33784) since the error occurs only in Chrome. Other browsers are rendering it just fine. There is a workaround by disabling “slimming paint” in Chrome.

Place this text in the URL of your Chrome browser:

```
chrome://flags/#disable-slimming-paint
```

Disable it.

The bug will remain until you restart Chrome.