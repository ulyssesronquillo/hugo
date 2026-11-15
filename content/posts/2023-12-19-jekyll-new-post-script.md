---
author: ulysses
title: 'jekyll new post script'
date: 2023-12-19
slug: jekyll-new-post-script
draft: false
---

Here's my bash script that creates a new Jekyll post template. Once created, use vi to edit the post.

```
#!/bin/bash
if [ "$#" -ne 1 ]
then
  echo "Missing argument. Usage: ./jekyllNewPost.sh new-post-title"
  exit
fi

cd ~/Code/docker/ulyme/_posts/
ts=$(date +%Y-%m-%d)

title=$1
filename=($ts-$title.md)

pretitle=$(echo "${title^}")
posttitle=$(echo $pretitle | tr "-" " ")

cat << EOF > $filename
---
layout: post
author: ulysses
title: '$posttitle'
---
EOF

echo "vi ~/Code/docker/ulyme/_posts/$filename"
```
