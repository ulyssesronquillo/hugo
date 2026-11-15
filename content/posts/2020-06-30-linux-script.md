---
title: 'linux script'
author: ulysses

date: 2020-06-30
slug: linux-script
draft: false
---

The script command records all your keystrokes and output into a file called typescript.

You can start recording by simply typing script.

```
script
Script started, file is typescript
df -h
ls -l
exit
```

Typing exit stops the recording. Just cat typescript to see your recording.

```
cat typescript
```