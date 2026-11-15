---
title: 'bash spacebar break'
author: ulysses

date: 2022-08-16
slug: bash-spacebar-break
draft: false
---

Here’s how to add breaks in your Bash scripts. The function is called spacebar.

```
function spacebar {
  echo 'Press spacebar to continue. Press Ctrl-C to exit.'
  stty -echo > /dev/null
  until read -r -n 1 -t 0.001 && [ "$REPLY" = ' ' ]; do abc=''; done
  stty echo > /dev/null
}

spacebar
```

You can call it multiple times in your script since it’s a function.