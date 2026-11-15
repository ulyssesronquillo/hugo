---
title: 'comment multiple lines in bash'
author: ulysses

date: 2017-11-28
slug: comment-multiple-lines-in-bash
draft: false
---

If you find yourself commenting out multiple lines in BASH, there is a simple way of commenting them out using the HERE DOCUMENT feature. Typically you use the hash (#) tag to comment out each line, but that can get tiresome especially if have hundreds of lines. Here’s a better option. Use the HERE DOCUMENT feature in BASH. Anything in between the HERE DOCUMENT will be ignored by BASH and treated as comments.

If you need to reverse them, then just do the following. In this way, you only have to touch 2 lines instead of multiple lines.
