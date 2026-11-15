---
author: ulysses
title: 'copy paste nvim'
date: 2026-01-18
slug: copy-paste-nvim
draft: false
---
How to copy and paste in vim or nvim.

Let's say you have 10 rows of code that you want to copy somewhere else like at the bottom of your code.

1. Press Esc to enter Normal mode.
2. Move the cursor to the first line.
3. Enter Visual Line mode. Shift+V. 
4. Move cursor or letter j or k.
5. Press y to yank the selected lines.
6. Move the cursor to your target location.
7. Press p to paste after the current line. 
8. Or P to paste before the current line.

```
Esc
Move cursor
Shift+V
Move cursor
y
Move cursor
p or P
u
```

If you want to undo, press u.
