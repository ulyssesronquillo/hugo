---
title: 'install go on linux mint 19.3'
author: ulysses

date: 2020-02-09
slug: install-go-on-linux-mint-19-3
draft: false
---

Here’s how to install Go on Ubuntu Linux Mint 19.3.

Download the latest from https://golang.org/dl/.

```
wget https://dl.google.com/go/go1.13.linux-amd64.tar.gz
```

Check the checksum.

```
sha256sum go1.13.linux-amd64.tar.gz
```

Extract the Go tarball to the /usr/local directory.

```
sudo tar -C /usr/local -xzf go1.13.linux-amd64.tar.gz
```

Edit your Bash profile to add Go’s path.

```
cd ~
vim ~/.profile
# Add Go's path
export PATH=$PATH:/usr/local/go/bin
# Load the profile
source ~/.profile
```

Check if Go is installed.

```
go version
```

Output.

```
go version go1.13 linux/amd64
```