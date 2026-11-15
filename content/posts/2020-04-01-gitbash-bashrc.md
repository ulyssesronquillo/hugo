---
title: 'gitbash .bashrc'
author: ulysses

date: 2020-04-01
slug: gitbash-bashrc
draft: false
---

Here’s how to find your GitBash .bashrc.

```
# cd takes you to gitbash home
cd 
# edit .bashrc
vim ~/.bashrc
```

You can add aliases, change prompt styles, etc.

```
export PS1="\w: $ "
alias gcloud="gcloud.cmd"
alias gsutil="gsutil.cmd"
alias code="cd ~/Code"
cd Code
```