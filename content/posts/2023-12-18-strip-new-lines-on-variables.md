---
author: ulysses
title: 'strip new lines on variables'
date: 2023-12-18
slug: strip-new-lines-on-variables
draft: false
---

I had problems echoing four variables into one line. There seem to be some carriage return or new line somewhere that's not visible.

So, here's a line of code that will strip any new line or carriage return in the variable, and then use printf to display the variables on one line.

Strip the new lines.

```
efs="${efs//$'\n'/ }"
name="${name//$'\n'/}"
total="${total//$'\n'/ }"
mesg="${mesg//$'\n'/}"
```

Now print them using printf on one line.

```
printf "%-30s %-40s %-20s %-30s\n" "$efs" "$new" "$total" "$mesg"
```

With that code, I'm now able to format my report nicely without the extra new lines.
