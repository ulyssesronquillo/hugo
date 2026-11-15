---
title: 'jq on gitbash'
author: ulysses

date: 2021-07-07
slug: jq-on-gitbash
draft: false
---

JQ is a json processor. It’s for slicing and dicing data.

[Download](https://stedolan.github.io/jq/)

To install on GitBash, unzip the file and copy the executable to /usr/bin.

```
mv jq-win64.exe to /usr/bin/jq.exe
```

Create an alias. Edit ~/.bashrc.

```
alias jq='/usr/bin/jq.exe'
```

Using JQ.

```
jq --version
jq '.selfLink' vm.json
```