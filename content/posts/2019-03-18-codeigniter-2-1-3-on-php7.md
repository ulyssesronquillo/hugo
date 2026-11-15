---
title: 'codeigniter 2.1.3 on php7'
author: ulysses

date: 2019-03-18
slug: codeigniter-2-1-3-on-php7
draft: false
---

If you’re still running older versions of CodeIgniter, here are a couple of tips to make it work with PHP7.

1. Make sure to install all PHP tools and libraries that comes with PHP7. I was missing curl.
2. Change your database driver from mysql to mysqli (application/config/config.php).
3. Fix the /system/core/Common.php [error](https://stackoverflow.com/questions/28348879/only-variable-references-should-be-returned-by-reference-codeigniter#28348880) or as some prefer, upgrade to a newer version.

Considering v2.1.3 is very old (currently 3.1.10) , I’m surprised it works with PHP7 with just a few modifications.