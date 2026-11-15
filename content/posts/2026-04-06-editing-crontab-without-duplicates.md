---
author: ulysses
title: 'editing crontab without duplicates'
date: 2026-04-06
slug: editing-crontab-without-duplicates
draft: false
---
Here's a neat script that will edit crontab without creating duplicates.

```
#!/usr/bin/env bash

CRON_ENTRY="0 2 * * * /path/to/script.sh"

EXISTING=$(crontab -l 2>/dev/null || true)

if ! echo "$EXISTING" | grep -Fxq "$CRON_ENTRY"; then
  printf "%s\n%s\n" "$EXISTING" "$CRON_ENTRY" | crontab -
fi
```
