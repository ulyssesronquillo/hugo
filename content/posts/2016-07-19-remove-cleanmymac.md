---
title: 'remove cleanmymac'
author: ulysses

date: 2016-07-19
slug: remove-cleanmymac
draft: false
---

Several months ago, I’ve installed an app called [CleanMyMac](http://macpaw.com/cleanmymac). Big mistake. I didn’t like it much. I deleted it shortly after. The uninstall didn’t quite exactly remove everything. This morning, I updated my computer with the latest Mac updates. It required a reboot. Sure enough, the CleanMyMac notifications came back. Apparently, there’s some pieces of the app that are still running on my machine.

The only way I was able to delete anything related to the CleanMyMac app was to use a couple of tools. One is called [Find Any File](http://apps.tempel.org/FindAnyFile/), a handy utility for finding obscure files in your OS. The other is the handy tool called the [Terminal](https://en.wikipedia.org/wiki/Terminal_(OS_X)). Start with the Find Any File app and search for files that contain the words “CleanMyMac” and “macaw.” The Find Any File app will show you a list of files and their locations. You should be able to delete the files directly from the app. However, there are some files that are write-protected. They can be deleted using a sudo account on the Terminal.

Open up your Terminal and start deleting the files using “[sudo rm](https://help.ubuntu.com/community/DeletingFiles)” command. You’ll be ask to provide the admin password. Don’t forget to empty the Trash.

That should do the trick.