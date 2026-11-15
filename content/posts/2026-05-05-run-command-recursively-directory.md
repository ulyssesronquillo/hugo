---
author: ulysses
title: 'run command recursively directory'
date: 2026-05-05
slug: run-command-recursively-directory
draft: false
---
Here's the script that will the dos2unix command recursively in the current directory.

It doesn't have to be dos2unix but can be any command.

Run it on all files.

```
find . -type f -exec dos2unix {} +
```

Run it on all shell files only.

```
find . -type f -name "*.sh" -exec dos2unix {} +
```
