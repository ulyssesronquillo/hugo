---
title: 'git switch from https to ssh'
author: ulysses

date: 2022-01-20
slug: git-switch-from-https-to-ssh
draft: false
---

If you have trouble cloning a github repo using https, you can tell it to switch to SSH instead.

Here’s the command.

```
git config --global url.ssh://git@github.com/.insteadOf https://github.com/
```

I had to specify reconfigure when I ran terraform init.

```
terraform init --reconfigure
```