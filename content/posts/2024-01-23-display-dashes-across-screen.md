---
author: ulysses
title: 'display dashes across screen'
date: 2024-01-23
slug: display-dashes-across-screen
draft: false
---

Here's the traditional way of displaying a list of dashes across the screen.

```
echo "===================="
```

Here's the short cut.

```
printf -- '=%.s' {1..20}; echo
```

Explanation:

- first I'm using printf instead of echo. printf is a little bit better when it comes to formatting.
- The -- option tells printf to ignore the rest of the remaining arguments so it renders properly.
- The character before the % percentage is the one being repeated. In this case, we are repeating "=."
- 1-20 is the number of times the character before the % percentage is repeated.

That's it.
