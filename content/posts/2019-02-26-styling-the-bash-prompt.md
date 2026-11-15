---
title: 'styling the bash prompt'
author: ulysses

date: 2019-02-26
slug: styling-the-bash-prompt
draft: false
---

Great [article](https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html) how to style your Bash prompt. Make sure you are using Bash shell, because you could be using another shell. Use this to display your current shell. Just type “bash” to start using Bash shell.

```
echo $0
bash
```

I use the prompt style below. See the result underneath PS1. You may have to exit and re-enter your Terminal to see results.

```
PS1="\u@\h:\w: "
ulysses@localhost:/var/www: 
```