---
author: ulysses
title: 'confirm random string'
date: 2026-04-21
slug: confirm-random-string
draft: false
---
Here's a nice little script that generates a random string.

User is asked to match the string. If there's a match, it continues.

If there's no match, it will exit.

```
confirm() {
  CHARNUM=6
  CHARSET='A-Za-z0-9'
  # Generate random string
  RANDOM_STRING=$(LC_ALL=C tr -dc $CHARSET </dev/urandom | head -c $CHARNUM)
  printf "%s\n" "Please confirm Code to continue: $RANDOM_STRING"
  read -r -p "Code: " USER_INPUT
  if [[ "$USER_INPUT" != "$RANDOM_STRING" ]]; then
    echo "❌ Code does not match! Exiting!"
    exit 1
  fi
  echo "✅ Code matched!"
  echo "Shutting down server!"
}
```

