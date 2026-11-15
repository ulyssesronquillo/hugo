---
title: 'upgrading icecast2'
author: ulysses

date: 2016-07-13
slug: upgrading-icecast2
draft: false
---

The following instructions will perform the latest Icecast2 server upgrade on your Ubuntu Server via the PPA route.

1. Login to your Ubuntu Server via SSH. Substitute your own username and server.

```
$ ssh ulysses@server.com
```

2. Add Icecast2 PPA to your sources list. Since I’m running Ubuntu 12.04, I’ll use the 12.04 repository here.

```
$ sudo sh -c "echo deb http://download.opensuse.org/repositories/home:/dm8tbr/xUbuntu_12.04 ./ > /etc/apt/sources.list.d/icecast.list"
```

3. Add the GPG key to the apt sources keyring. I’ll use the 12.04 release key here as well.

```
$ wget -qO - http://download.opensuse.org/repositories/home:/dm8tbr/xUbuntu_12.04/Release.key | sudo apt-key add -
```

4. Run Update to begin the upgrade process to the latest version of Icecast2.

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

5. The Icecast2 install script will run and ask you to overwrite your previous configuration. It’s up to you to keep or overwrite the file.

6. If you’re using your previous configuration file, it may throw out some errors and warnings, which you will probably need to fix.

7. Finally, test your Icecast2 server by sending a stream to it.