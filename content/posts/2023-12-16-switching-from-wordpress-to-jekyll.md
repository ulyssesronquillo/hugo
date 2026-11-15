---
author: ulysses
title: 'switching from wordpress to jekyll'
date: 2023-12-16
slug: switching-from-wordpress-to-jekyll
draft: false
---

I recently migrated this blog from WordPress to Jekyll due to several reasons. 

It came down to these three reasons:

- Cost
- Speed
- Security

1. Cost. Jekyll generates static websites, meaning it can be hosted freely at Github. No more hosted VM's. That's a savings of $120 per year.
2. Speed. Since Jekyll pages are static HTML pages, websites loads much faster. There are no more PHP, extra plugins or databases that slow down pages.
3. Security. Since Jekyll pages are static files, they do not need a LAMP stack. So no more OS, PHP, plugins or MySQL databases to securely maintain.

It's a win win. The migration was quick and easy, but not it's not entirely a 100% bug-free. I had to tweak Jekyll templates here and there to get it to look the way I wanted it. There are a ton of articles out there that covers the Jeklly to WordPress migration. I'm not going to cover the migration process here step by step. To quickly summarize, you'll need to install a Jekyll exporter plugin in WordPress to export your posts. You can then import your posts into Jekyll and tweak Jekyll the way you want it. That's it in a nutshell. 

By the way, I'm running Jekyll in a Docker. If you are interested, here are the [instructions]({% post_url 2022-08-31-jekyll-on-docker-container %}) to run Jekyll in a Docker container.
