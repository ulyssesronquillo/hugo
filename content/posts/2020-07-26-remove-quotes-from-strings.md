---
title: 'remove quotes from strings'
author: ulysses

date: 2020-07-26
slug: remove-quotes-from-strings
draft: false
---

Here’s the command to remove quotes from a string in Bash by using the tr -d command. I’m using jq tool to extract the access key from a json file. Bash returns a string surrounded by quotes. To remove the quotes, just pipe the string to the tr -d command.

```
jq .AccessKey.AccessKeyId key.json 
```

Result:

```
"ASDFSDFSDFASDFSDFSDFGHGDF"
```

Using tr -d.

```
jq .AccessKey.AccessKeyId key.json | tr -d \"
```

Result:

```
ASDFSDFSDFASDFSDFSDFGHGDF
```