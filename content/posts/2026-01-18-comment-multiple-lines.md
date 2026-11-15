---
author: ulysses
title: 'comment multiple lines'
date: 2026-01-18
slug: comment-multiple-lines
draft: false
---
How to comment multiple lines in nvim.

1. Go to the first line you want to start to comment. Place cursor at the beginning.
2. Enter Visual Block mode by pressing Ctrl+v.
3. Use arrow keys or j to select multiple lines.
4. Shift+I to enter insert mode.
5. Choose a character (#) to use.
6. Esc to comment multiple lines.

```
Ctrl+v
Use cursor or j
Shift+I
#
Esc
```

To uncomment

1. Place cursor on the first comment.
2. Enter Visual Block or Ctrl+v.
3. Select columns using cursor or j,k.
4. Press x or d to delete on selected lines.

```
Ctrl+v
Use cursor or j
x or d
```
