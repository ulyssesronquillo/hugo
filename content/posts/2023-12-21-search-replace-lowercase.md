---
author: ulysses
title: 'Search replace lowercase'
date: 2023-12-21
slug: search-replace-lowercase
draft: false
---

Here's a script I use to edit over 1000 files to convert my post titles to all lowercase.

```
#!/bin/bash 
cd ~/Code/docker/ulyme/_posts
searchReplace() {
    for filename in 20*.md; do
        sed -i -e 's/title:.*/\L&/g' $filename
    done
}
searchReplace

```

It took a mere 2-3 seconds to convert all titles on over 1000 files.
