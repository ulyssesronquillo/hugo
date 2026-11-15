---
title: 'add path to zsh'
author: ulysses

date: 2021-11-06
slug: add-path-to-zsh
draft: false
---

Here’s how to add a path to zsh permanently.

Edit .zshrc file and add the path. Create .zshrc file if it’s missing.

```
export PATH=$PATH:/new/path
```

Exit and relaunch shell. The new path should be in effect.

Echo to display new path.

```
echo $PATH
```