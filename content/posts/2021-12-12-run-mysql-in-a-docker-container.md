---
title: 'run mysql in a docker container'
author: ulysses

date: 2021-12-12
slug: run-mysql-in-a-docker-container
draft: false
---

How to run MySQL commands in a Docker container.

```
#!/bin/bash
set -a; source /dev/null
```

- The first command loads the content of .env to environment variables.
- The MySQL password can then be used using the ${MYSQL\_PASSWORD} variable.
- I’m using sed to get around the special characters in the password.
- The second command runs docker exec on wp\_db container.
- The last 3 commands are the actual sql commands.
- We are selecting to use the db1 database.
- Then we run select statements from the wp\_options table.
- Finally, 2&gt;/dev/null suppresses errors and warning to null.