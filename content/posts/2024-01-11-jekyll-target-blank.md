---
author: ulysses
title: 'jekyll target blank'
date: 2024-01-11
slug: jekyll-target-blank
draft: false
---

I found a really nice gem that sets all external links to open to a new tab. It's called jekyll-target-blank. To add, just run the following.

Edit Gemfile and add this line.

```
gem 'jekyll-target-blank'
```

Edit the &#95;config.yml file and add this line.

```
plugins:
  - jekyll-target-blank
```

Run bundle install.

```
$ bundle install
```

Because I'm running Jekyll in a docker container, I had to restart it.

```
docker-compose stop
docker-compose up -d
```

Check your external links. They should open up to a new tab.
