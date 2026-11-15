---
title: 'bash any key'
author: ulysses

date: 2022-11-29
slug: bash-any-key
draft: false
---

Here’s the script to add pauses in your Bash script.

```
echo "please wait until web page loads ... "
read -p "Press any key to continue... " -n1 -s
```

You can also put it inside a function and call it multiple times.

```
function press_any_key {
  echo "please wait until web page loads ... "
  read -p "Press any key to continue... " -n1 -s
}
press_any_key
```