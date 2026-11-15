---
title: 'bash menu and functions'
author: ulysses

date: 2022-09-22
slug: bash-menu-and-functions
draft: false
---

How to integrate menus and functions in your Bash script.

```
#!/bin/bash
function show_logs {
ls -l /var/log/
}
function show_users {
cat /etc/passwd
}
echo '--------'
echo 'My Menu'
echo '--------'
PS3='Choose an option: '
commands=("Show logs" "Show users" "Quit")
COLUMNS=0
select cmd in "${commands[@]}"; do
    case $cmd in
        "Show logs")
            echo "Showing logs ... "
            show_logs
            ;;
        "Show users")
            echo "Showing users ... "
            show_users
            ;;
	"Quit")
	    echo "Exiting ... "
	    exit
	    ;;
        *) echo "invalid option $REPLY";;
    esac
done
```

Result

```
--------
My Menu
--------
1) Show logs
2) Show users
3) Quit
```