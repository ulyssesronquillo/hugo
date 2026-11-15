---
title: 'regex match'
author: ulysses

date: 2019-01-19
slug: regex-match
draft: false
---

Regex is really cool. You can do amazing things with it, but if you’re starting new, it’s quite daunting task. If you ever find one that works, you better hang on to it for dear life. Here’s one that I know is working. It reads data from a file, and compares and matches a variable to a certain pattern. In the example below, the variable I’m searching for, must contain a string with the following characters “server-w.” They also must be followed by at least one number or a set of numbers.

```
cat filename | while read LINE; do
  if [[ $LINE =~ server-w-*.[0-9] ]]; then
     echo "Do not backup $LINE"
  else
     echo "Backup $LINE"
  fi
done
```

If you need help with Regex, check out a couple of sites below that allows you to test your regex skills. [Regex](https://www.regextester.com/) and [RegExr](https://regexr.com/).

[](https://regexr.com/)