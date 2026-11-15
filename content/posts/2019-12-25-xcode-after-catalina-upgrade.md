---
title: 'xcode after catalina upgrade'
author: ulysses

date: 2019-12-25
slug: xcode-after-catalina-upgrade
draft: false
---

I tried running git after the Mac OS Catalina upgrade and got this error.

```
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools),
missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```

Here’s the fix. For some very odd reason, Apple does not automatically reinstall xcode after each Mac OS upgrade.

You will need to either reset it or install it again.

```
# Try reset first
xcode-select --reset
# Or install it if reset doesn't work
xcode-select --install
```

Close your terminal, and reopen and run git again.