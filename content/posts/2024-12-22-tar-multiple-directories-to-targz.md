---
author: ulysses
title: 'tar multiple directories to targz'
date: 2024-12-22
slug: tar-multiple-directories-to-targz
draft: false
---

Tar multiple directories to a single tar.gz file.

```
tar -czvf /home/ulysses/Code/backup.tar.gz ~/Documents/ ~/Downloads ~/Git/gcloud/ ~/Pictures ~/Videos
```

To list files inside the tar.gz file, run this.

```
tar -tzvf /home/ulysses/Code/backup.tar.gz
```
