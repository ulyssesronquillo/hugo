---
author: ulysses
title: 'more search and replace'
date: 2025-12-04
slug: more-search-and-replace
draft: false
---
A couple of years ago, I converted this website from WordPress to Jekyll. At that time, I didn't bother removing some header data that came with WordPress because it was tedious. It required editing over 1100 files. But with the help with some search and replace commands, I was able to mass delete specific lines from 1130 files in less than 5 minutes. Here are the search and replace commands I ran.

Remove "id:" and "date:" lines.

```
find . -type f -exec sed -i '/id: /d' {} +
find . -type f -exec sed -i '/date: /d' {} +
```

Remove lines starting from "categories:" up to "---".

```
find . -type f -exec sed -i '/^categories:/,/^---/ { /^---/! d }' {} +
```

Finally, remove lines from "wp-syntax-cache-content" up to "---".

```
find . -type f -exec sed -i '/^wp-syntax-cache-content:/,/^---/ { /^---/! d }' {} +
```

Needless to say, the blog looks the same, but the file structure beneath it is dramatically different.
