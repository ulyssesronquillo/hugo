---
title: 'press spacebar to continue'
author: ulysses

date: 2022-08-05
slug: press-spacebar-to-continue
draft: false
---

Here’s a little snippet of Bash code that waits for spacebar to be pressed to continue.

```
function spacebar {
  echo 'Press spacebar to continue. Press Ctrl-C to exit.'
  stty -echo > /dev/null
  until read -r -n 1 -t 0.001 && [ "$REPLY" = ' ' ]; do abc=''; done
  stty echo > /dev/null
}
echo 'Starting upgrade'
spacebar
```

Output

```
Starting upgrade
Press spacebar to continue. Or Ctrl-C to exit.
```

If you press spacebar it will continue. Ctrl-C exits the program.