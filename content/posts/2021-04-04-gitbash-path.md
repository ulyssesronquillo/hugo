---
title: 'gitbash path'
author: ulysses

date: 2021-04-04
slug: gitbash-path
draft: false
---

Open Git Bash. Change to the root directory of Git Bash.

```
cd ~
echo $PATH
/bin:/c/Program Files (x86)/Google/Cloud SDK/google-cloud-sdk/bin
```

Edit .bash\_profile or .bashrc. It was .bash\_profile in my case. Showing a truncated path.

Add your custom path to the PATH variable. Save file. Exit Git Bash.

```
PATH="/bin:/c/Program Files (x86)/Google/Cloud SDK/google-cloud-sdk/bin:/c/custom/path"
```

Open Git Bash again and check your updated Path.

```
echo $PATH
```

Result.

```
/bin:/c/Program Files (x86)/Google/Cloud SDK/google-cloud-sdk/bin:/c/custom/path
```