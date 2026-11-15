---
title: 'gutenberg youtube embed'
author: ulysses

date: 2019-01-20
slug: gutenberg-youtube-embed
draft: false
---

The Gutenberg Youtube embed lacks a few things. The alignment doesn’t seem to be working, at least in the theme I’m using. I’m using Generate-Pro, a Genesis child theme. By default, it’s left-aligned. I have to add this div to make it centered.

```
<div style="text-align:center">
</div>
```

If you want right aligned, use this div.

```
<div style="text-align:right">
</div>
```