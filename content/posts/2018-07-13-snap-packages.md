---
title: 'snap packages'
author: ulysses

date: 2018-07-13
slug: snap-packages
draft: false
---

Ubuntu 16.04 has a feature called Snap packaging. Snaps are containerized software packages that are simple to create, and easy to install on all major Linux systems. Snap packages are self-contained and separate from your system files. There are no complex dependencies or interference. The packages are safe to run since snap packages and their data are separate from your system files. Updates are automatic and only download what has changed. You can revert to a previous version at any time. Any updates can also be reversed.

To install snap in Ubuntu, run this command from the Terminal.

```
$ sudo apt install snapd
```

To install snap packages, run the following:

```
$ sudo snap install packagename
```

To get a list of packages installed on your system:

```
$ snap list
```

To automatically update the packages, just run the following:

```
$ sudo snap refresh packagename
```

To revert changes or remove a package, perform the following:

```
$ sudo snap revert packagename
$ sudo snap remove packagename
```

Super easy to use.