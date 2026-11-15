---
title: 'route 53 policy to change records'
author: ulysses

date: 2019-06-14
slug: route-53-policy-to-change-records
draft: false
---

Here’s the IAM policy you’ll need to change Route 53 DNS records. Substitute with your own hosted zone id.

```
{
   "Statement":[{
      "Effect":"Allow",
      "Action":["route53:ChangeResourceRecordSets"],
      "Resource":"arn:aws:route53:::hostedzone/*HOSTEDZONEID*"
      }
   ],
   "Statement":[{
      "Effect":"Allow",
      "Action":["route53:GetChange"],
      "Resource":"arn:aws:route53:::change/*"
      }
   ]
}
```

Add to policy to a user.