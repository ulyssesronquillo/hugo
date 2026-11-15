---
title: 'vim colors'
author: ulysses

date: 2022-10-25
slug: vim-colors
draft: false
---

I had trouble getting my vi editor to display all black background color. This includes the background color after the end of the file. I just wanted an all black background for better visibility. I did a little bit of googling and found this nice little gem. I happen to like the dessert theme and went with that instead of the recommended mustang theme which I don’t have installed. Hope you’ll find this helpful.

```
set t_Co=256
set background=dark
colorscheme dessert
highlight Normal ctermbg=NONE
highlight nonText ctermbg=NONE
```