---
title: 'check db connection on aws'
author: ulysses

date: 2017-12-03
slug: check-db-connection-on-aws
draft: false
---

When setting up your cloud infrastructure, you can check if your instances have access to the database by performing this command.

```
$ nc -zv 10.0.0.45 3306
$ nc -zv domain.com 3306
$ nc -zv endpoint.amazonaws.com 3306
```

If connection has succeeded, you’ll get a message like this in Linux and MacOS …

```
Connection to endpoint.amazonaws.com 3306 port [tcp/mysql] succeeded!
```

On Windows, you can use Telnet to test your DB connection.

```
C:\>telnet endpoint.amazonaws.com 3306
```

If connection has succeeded, the result is “no message.” If there’s a problem, you’ll get this ….

```
Connecting To endpoint.amazonaws.com...Could not open 
connection to the host, on port 3306: Connect failed 
```