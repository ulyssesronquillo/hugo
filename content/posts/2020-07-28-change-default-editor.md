---
title: 'change default editor'
author: ulysses

date: 2020-07-28
slug: change-default-editor
draft: false
---

Ubuntu and Linux Mint use nano as their default editor. You’ll see it if you try to edit crontab or visudo. Now, there’s nothing wrong with nano, but I prefer using vim instead. Here’s how to change the default editor.

```
sudo update-alternatives --config editor
```

You’ll be prompted to change the default editor.

```
There are 4 choices for the alternative editor (providing /usr/bin/editor).

  Selection    Path                Priority   Status
------------------------------------------------------------
  0            /bin/nano            40        auto mode
  1            /bin/ed             -100       manual mode
  2            /bin/nano            40        manual mode
* 3            /usr/bin/vim.basic   30        manual mode
  4            /usr/bin/vim.tiny    15        manual mode

Press <enter> to keep the current choice[*], or type selection number: 
</enter>
```

Type 3 to choose vim basic.