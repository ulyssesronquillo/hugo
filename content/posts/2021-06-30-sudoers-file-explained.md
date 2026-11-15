---
title: 'sudoers file explained'
author: ulysses

date: 2021-06-30
slug: sudoers-file-explained
draft: false
---

You are probably wondering how the sudoers file works. Here’s a simple explanation.

Command

```
username host=(user:group) tag:commands
```

Explanation

- - username – the specified user allowed to run commands.
    - host – the specified host the command is allowed to run.
    - user – specifies which users can use the command.
    - group – specifies which groups can run the command.
    - tag – the option allowed. NOPASSWD
    - command – the command allowed to run.

Examples

```
root    ALL=(ALL) ALL
username ALL=(ALL) ALL
john test=(ALL) NOPASSWD: /bin/useradd
jane ALL=(sales) NOPASSWD: /bin/sh
%sudo ALL=(ALL) ALL
%adgroup ALL=(ALL) ALL
```