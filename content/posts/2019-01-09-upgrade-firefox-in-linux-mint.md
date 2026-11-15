---
title: 'upgrade firefox in linux mint'
author: ulysses

date: 2019-01-09
slug: upgrade-firefox-in-linux-mint
draft: false
---

I fired up my old Linux PC which runs on Linux Mint. I noticed the default Firefox browser is quite old. It needs an upgrade, which is expected since this Linux Mint version is 18.1. The current version is 19.1. So, here are the steps to upgrade Firefox in Linux Mint.

Download Firefox.

```
wget https://www.mozilla.org/en-US/firefox/download/thanks/
```

Extract.

```
cd ~/Downloads/
tar xjf firefox-64.0.2.tar.bz2
```

Move Firefox.

```
mv firefox /opt/firefox
```

Create a symbolic link.

```
ln -s /opt/firefox/firefox /usr/bin/firefox
```

The old icons should still work. Enjoy.