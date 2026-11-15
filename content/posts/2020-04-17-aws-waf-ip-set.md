---
title: 'aws waf ip set'
author: ulysses

date: 2020-04-17
slug: aws-waf-ip-set
draft: false
---

Here’s how to get the WAF rule.

```
aws waf-regional get-rule \
--rule-id xxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Here’s how to get the AWS WAF IP set.

```
aws waf-regional get-ip-set \
--ip-set-id xxxxxxxxxxxxxxxxxxx \
--region us-east-1 \
--profile your-profile
```

Here’s how to get the latest token.

```
aws waf-regional get-change-token
```

Result is similar to this.

```
{
    "ChangeToken": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

Create a JSON file called “change.json” to be used for updating the IP set. We will insert and delete an IP set.

```
[
    {
        "Action": "INSERT",
        "IPSetDescriptor":
        {
            "Type": "IPV4",
            "Value": "12.34.56.78/24"
        }
    },
    {
        "Action": "DELETE",
        "IPSetDescriptor":
        {
            "Type": "IPV6",
            "Value": "1111:0000:0000:0000:0000:0000:0000:0111/128"
        }
    }
]
```

Finally, here’s how to update the IP set.

```
aws waf-regional update-ip-set \
--ip-set-id xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx \
--change-token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx \
--region us-east-1 \
--profile default \
--updates file://change.json
```