---
title: 'nano history error'
author: ulysses

date: 2013-12-20
slug: nano-history-error
draft: false
---

I experienced a “nano” editor error this morning. It displayed this:

```
Error reading /home/ulysses/.nano_history: Permission denied
Press Enter to continue starting nano.
```

The error doesn’t prevent you from using the nano editor, but it displays an annoying message. You have to press the Enter key each time you want to use the editor. I’m not sure how I manage to make the nano editor behave this way. I probably edited a file in my home directory while I was root. It’s a common mistake.

So, when accessed as a regular user, I simply didn’t have permissions to the nano history. A simple fix for this is to delete the .nano\_history file while logged in as root. Switch back as a regular user and run nano again. Nano will re-create the history file the next time you use it.

```
$ sudo rm /home/ulysses/.nano_history
```

That should take care of it.