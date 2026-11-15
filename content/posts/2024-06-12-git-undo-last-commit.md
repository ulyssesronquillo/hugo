---
author: ulysses
title: 'git undo last commit'
date: 2024-06-12
slug: git-undo-last-commit
draft: false
---
How to undo git's last commit.

```
git reset --soft HEAD~
```

Undo the last 2 commits. 

```
git reset --soft HEAD~2
```

Undo local changes.

```
git reset --hard abcd543
```

