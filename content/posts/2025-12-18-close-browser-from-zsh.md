---
author: ulysses
title: 'close browser from zsh'
date: 2025-12-18
slug: close-browser-from-zsh
draft: false
---
There's a command to close a browser tab or window from zsh on a Mac OS.

You have to specify which browser you're using.

As well as the current URL of the tab.

```
osascript -e 'tell application "Google Chrome" to close (tabs of windows whose URL contains "uly.me")'
```

Give it a try.
