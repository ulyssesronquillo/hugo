---
title: 'install latest sublime text'
author: ulysses

date: 2021-12-31
slug: install-latest-sublime-text
draft: false
---

How to install the latest version of the Sublime Text editor on Ubuntu or Mint.

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```

It will add the sublime-text.list file in /etc/apt/sources.list.d directory.