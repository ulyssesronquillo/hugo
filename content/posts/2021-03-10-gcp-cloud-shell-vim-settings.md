---
title: 'gcp cloud shell vim settings'
author: ulysses

date: 2021-03-10
slug: gcp-cloud-shell-vim-settings
draft: false
---

I had an issue with using the backspace in Vim in GCP’s Cloud Shell. Every time I’m in the insert mode and I want to edit using backspace, it doesn’t delete the characters. It shows these characters “^?” instead. Well, it turned out to be a backspace setting that you can set within .vimrc. So, here’s my working setup.

```
colo desert
syntax on
set backspace=indent,eol,start
set nocompatible
```

- The first line uses the desert theme.
- The second line turns on syntax highlighting. It’s on by default.
- The third line fixes the backspace issue I mentioned above.