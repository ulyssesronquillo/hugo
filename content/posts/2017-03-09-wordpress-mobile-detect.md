---
title: 'wordpress mobile detect'
author: ulysses

date: 2017-03-09
slug: wordpress-mobile-detect
draft: false
---

I found this little nugget in the [WordPress Codex](https://codex.wordpress.org/Function_Reference/wp_is_mobile) called wp\_is\_mobile(). It will detect the user browser’s agent and will return a true or a false if it’s a mobile device. This is helpful if you would like to customized code specifically for a mobile device. Let’s say you have a media player and you want it to have a specific width for desktops and another width for mobile devices. So, here’s the code to detect if it’s a mobile device.

```
if ( wp_is_mobile() ) :
  $player_width = '270';
else :
  $player_width = '400';
endif;
```

You can then use the variable **$player\_width** in your media player configuration to set the width of the player. However, if you read the Codex, it says that tablets are considered as mobile devices, which is perfectly fine for my purposes here. It’s ok to use this tiny little function in your WordPress templates, but it’s not recommended for media queries.