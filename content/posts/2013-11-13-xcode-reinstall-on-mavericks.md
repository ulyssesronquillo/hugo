---
title: 'xcode reinstall on mavericks'
author: ulysses

date: 2013-11-13
slug: xcode-reinstall-on-mavericks
draft: false
---

I’ve been using Mac OS 10.9 Mavericks for a couple of weeks now. So far, so good. No issues whatsoever. There were several updates that followed the OS upgrade. Updates to iTunes, iMovie, iPhoto were the obvious ones, plus a couple of other small applications that were also updated as a result of the OS upgrade.

I happen to use Git for version control for my software projects. One thing I noticed after upgrading to Mavericks, Git stopped working completely. I tried to do a git pull, and I was met with this error, “xcode-select: note: no developer tools were found at ‘/Applications/Xcode.app’, requesting install. Choose an option in the dialog to download the command line developer tools.”

The cool part about all this is, Mavericks immediately recognized the problem and offered to correct it by asking the user to proceed with Xcode installation. I gladly clicked Update/Install. The update took less than 5 minutes to complete. After the install, I issued git pull command again, and sure enough the my git repository updated nicely.

I’m glad to report that after two weeks running on Mac OS Mavericks, I haven’t had any major problems, except for this relatively minor inconvenience of reinstalling Xcode.