---
title: 'display asterisks when typing passwords in bash'
author: ulysses

date: 2023-09-18
slug: display-asterisks-when-typing-passwords-in-bash
draft: false
---

Here’s how to display asterisks when typing passwords in Bash.

```
#!/bin/bash
unset password
prompt="Enter Password:"
while IFS= read -p "$prompt" -r -s -n 1 char
do
    if [[ $char == $'\0' ]]
    then
        break
    fi
    prompt='*'
    password+="$char"
done
echo
echo "Done. Password=$password"
```