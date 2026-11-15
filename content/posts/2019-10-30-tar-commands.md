---
title: 'tar commands'
author: ulysses

date: 2019-10-30
slug: tar-commands
draft: false
---

Here are two important tar commands on how to create and extract a tar.gz file.

Create a tar gzip file called “project.tar.gz” of a directory called “foo.”

 ```
tar -cvzf project.tar.gz foo
```

Untar the “project.tar.gz” file to a directory called bar.

 ```
tar -xvzf project.tar.gz bar
```