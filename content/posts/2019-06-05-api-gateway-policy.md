---
title: 'api gateway policy'
author: ulysses

date: 2019-06-05
slug: api-gateway-policy
draft: false
---

This policy gives a user access to the API gateway.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "apigateway-policy",
            "Effect": "Allow",
            "Action": [
                "apigateway:DELETE",
                "apigateway:PUT",
                "apigateway:PATCH",
                "apigateway:POST",
                "apigateway:GET"
            ],
            "Resource": "*"
        }
    ]
}
```