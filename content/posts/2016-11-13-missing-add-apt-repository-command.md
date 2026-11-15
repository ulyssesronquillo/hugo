---
title: 'missing add-apt-repository command'
author: ulysses

date: 2016-11-13
slug: missing-add-apt-repository-command
draft: false
---

When adding a new repository in Ubuntu, you can go the PPA route by using the add-apt-repository command. If you’re getting a missing add-apt-repository command, it’s probably not installed. You need to install the “software-properties-common” and “python-software-properties” packages from the Terminal. By the way, if you’re curious, PPA means personal package archive. PPAs are repositories hosted on Launchpad which you can use to install or upgrade packages that are not available in the official Ubuntu repositories. Just think of them as extended repositories.

If you’re getting a missing add-apt-repository command, just install the following:

```
$ sudo apt-get install software-properties-common python-software-properties
```

Once installed, you can then add other repositories that you want.

Let’s say you want to install Sublime Text 2, a real popular text editor.

You can install Sublime Text 2 via the PPA route using the following.

```
$ sudo add-apt-repository ppa:webupd8team/sublime-text-2
$ sudo apt-get update
$ sudo apt-get install sublime-text-2
```

Or install the latest Gimp release:

```
sudo add-apt-repository ppa:otto-kesselgulasch/gimp
sudo apt-get update
sudo apt-get install gimp
```

To revert the changes:

```
sudo apt-get install ppa-purge
sudo ppa-purge ppa:otto-kesselgulasch/gimp
```