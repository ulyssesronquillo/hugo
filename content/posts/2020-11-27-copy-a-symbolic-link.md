---
title: 'copy a symbolic link'
author: ulysses

date: 2020-11-27
slug: copy-a-symbolic-link
draft: false
---

Here’s how to copy a symbolic link which is also known as a soft link from one directory to another. A regular copy command will not work. You will need to use the -P option to copy the symbolic link from one directory to another. If omitted, the symbolic links will not be copied.

```
cp -P /directory1/* /directory2/
```

How to create a symbolic link.

```
ln -s sourcefile myfile
ln -s /path/to/file myfile
```

Here are the man pages for [ln](https://man7.org/linux/man-pages/man1/ln.1.html) and for [cp](https://linux.die.net/man/1/cp).