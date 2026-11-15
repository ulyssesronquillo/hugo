---
title: 'logging commands'
author: ulysses

date: 2021-02-22
slug: logging-commands
draft: false
---

I decided to log my commands for good record keeping. Here’s my script.

```
#!/bin/bash
if [[ $# -eq 0 ]] ; then echo 'No arguments. Format: ./go.sh script.sh'; exit 0; fi
log=log.txt
echo '-------------------------------' >> $log
date >> $log
echo '---' >> $log
cat $1 >> $log
echo '---' >> $log
/bin/bash $1 2>&1 | tee -a $log
```

To run.

```
./go.sh script.sh
```

Line by line explanation.

1. Checks for script to run. Exits if there’s no argument.
2. Sets the log file.
3. Prints dashes.
4. Prints the date.
5. Print 3 dashes.
6. Prints the commands to the log file.
7. Print 3 dashes.
8. Run the command. Send error and standard out to log file.