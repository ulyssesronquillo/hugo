---
title: 'create a repository in codecommit'
author: ulysses

date: 2018-07-22
slug: create-a-repository-in-codecommit
draft: false
---

[CodeCommit](https://docs.aws.amazon.com/codecommit/latest/userguide/welcome.html) is a version control system hosted in AWS that you can use privately to store and manage your source code, documents or binary files. You can get free (as in beer) unlimited repositories, if you have less than 5 users, and if your storage is less than 50 GB-month, and you have less than 10,000 git requests per month. If you have more than 5 users, it’s $1 a month per user. Still not bad. Here’s CodeCommit [pricing](https://aws.amazon.com/codecommit/pricing/).

Create a repository in CodeCommit via the [Console](https://docs.aws.amazon.com/codecommit/latest/userguide/how-to-create-repository.html#how-to-create-repository-console) or the CLI.

```
aws codecommit create-repository --repository-name myrepo --repository-description "My repository"
```

Create in another region.

```
aws codecommit create-repository --region us-west-2 --repository-name myrepo --repository-description "My repository"
```

Enjoy.