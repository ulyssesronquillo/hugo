---
title: 'sanitize input'
author: ulysses

date: 2012-11-18
slug: sanitize-input
draft: false
---

When designing web applications, it’s important to sanitize data before storing them into the database. I use several PHP built-in functions namely trim, strip\_tags, htmlspecialchars, and addslashes to sanitize my forms. This function has become a staple for all my web projects. So, here it is.

```
function sanitize($in) {
  return addslashes(htmlspecialchars(strip_tags(trim($in))));
}
```

Whenever I need to sanitize a form input, I simply use the sanitize function before storing the data to the database.

```
$_POST['firstname'] = sanitize($_POST['firstname']);
```