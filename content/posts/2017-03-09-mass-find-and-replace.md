---
title: 'mass find and replace'
author: ulysses

date: 2017-03-09
slug: mass-find-and-replace
draft: false
---

There are situations when you have to do a mass find and replace on your database. Let’s say you’re really, really bad speller. You just recently found out that you’ve been spelling a word for wrongly for years. To avoid embarrassment, you decide to do a search and replace. Unfortunately, you found out that there are hundreds of posts that contains that misspelled word. Instead of editing each post which is time consuming, you decide to run a mass find and replace against the database. In this example, we will replace the word ‘dawg’ with ‘dog.’

```
UPDATE wp_posts SET post_content = REPLACE ( post_content, 'dawg', 'dog');
```

I highly recommend that you back up your database first. I also recommend that you run it on a test database first before running it on a production environment, because a mass update is quite dangerous if you’re not sure what you are doing. If you’re a WordPress user, there’s a plugin called Search and Replace that will do the same thing. That might be easier for most people who don’t have access to MySQL command line or PHPMyAdmin.