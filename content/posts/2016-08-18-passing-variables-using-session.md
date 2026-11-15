---
title: 'passing variables using session'
author: ulysses

date: 2016-08-18
slug: passing-variables-using-session
draft: false
---

Passing variables via the URL in PHP can be dangerous. This is the case if you don’t properly filter and sanitize your inputs. This could lead to potential database exploits via SQL injections. If you are using a download script, someone might be able traverse your directories and gain access to your system files. After all, you don’t want anyone looking at your passwd file. Back to PHP, it’s ideal if that we avoid passing variables via URL. We can use sessions.

Passing Variables via URL

```
// A variable is passed from one page to another via a link.
<a href="page2.php?file=sample.txt">Link</a>
// Someone can traverse the directory and access system files.
<a href="page2.php?file=../../../../../etc/passwd">Link</a>
```

Passing variables via Sessions

```
// Page 1
// start a session
session_start();
// set filename
$file = 'sample.txt';
$_SESSION['file']=$file;
<a href="page2.php">Page 2</a>
```

```
// Page 2
// start a session
session_start();
$file=$_SESSION['file']);
// display filename
echo $file;
// remove a session variable
unset($_SESSION['file']); 
// unset entire session
session_destroy();
```

Viewer must accept cookie for sessions to work.

Sessions are not foolproof. They can be hijacked, but they are a heck more secure than passing variables via the URL.