---
title: 'gimp on mac os x'
author: ulysses

date: 2013-12-18
slug: gimp-on-mac-os-x
draft: false
---

[Gimp](http://www.gimp.org) is the GNU image manipulation program that I use exclusively for editing and creating image files. It’s open-source and it’s free. Gimp on the Mac OS X has come a long way. Last year, Gimp went native on OS X, meaning it no longer required XQuartz or Apple’s X11 to run on the Mac OS.

When Apple released Mac OS X [Mavericks](http://www.apple.com/osx/) a couple of months ago, Gimp followed with its own release supporting Mavericks. However, there are some serious bugs that need fixing, particularly with the keyboard focus. When Gimp is prompted with a text box, the keyboard focus remains in the background.

Typing something in text box results in either nothing or some odd behavior in the background. Fortunately, there’s a temporary workaround with the keyboard focus issue. You must disable the keyboard shortcuts. You can do that by accessing Preferences &gt; Interface &gt; Remove All Keyboard Shortcuts.

The problem disappears once the keyboard shortcuts are disabled. I don’t really use keyboard shortcuts, so it doesn’t affect me. However, there are others that may be dependent on them. Hopefully, there will be a fix soon.