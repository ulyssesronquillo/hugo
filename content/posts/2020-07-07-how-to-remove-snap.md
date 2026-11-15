---
title: 'how to remove snap'
author: ulysses

date: 2020-07-07
slug: how-to-remove-snap
draft: false
---

Snap is cool, but not for everyone. To remove, follow these steps.

```
# get list
snap list
# remove snaps. repeat for each app.
snap remove chromium
# remove snapd
apt purge snapd
# remove snap from home
rm -rf ~/snap
# clean up cache
rm -rf /var/cache/snapd
apt purge snapd
```