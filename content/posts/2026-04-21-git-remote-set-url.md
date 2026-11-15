---
author: ulysses
title: 'git remote set url'
date: 2026-04-21
slug: git-remote-set-url
draft: false
---
I run Gitea on my desktop. Recently my desktop IP address changed. 

I should really set it to a static IP address, but that's another story. 

Doing a git pull and a git push no longer works since the remote URL changed. 

To update to a new remote location, simply run the command below. 

```
git remote set-url origin http://192.168.68.105:3000/ulysses/scripts.git
```

If you use SSH, use the SSH remote link instead of HTTP.
