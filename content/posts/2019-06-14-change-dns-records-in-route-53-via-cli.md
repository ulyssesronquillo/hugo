---
title: 'change dns records in route 53 via cli'
author: ulysses

date: 2019-06-14
slug: change-dns-records-in-route-53-via-cli
draft: false
---

How to change DNS records in Route 53 via AWS CLI.

- Assuming AWS CLI is already configured
- Uses Route53 change-resource-record-sets to update DNS records
- Substitute with your own hosted-zone-id
- Uses JSON files containing record sets
- See JSON file examples below

```
cd /path/to/scripts/
# the command to switch to the elb
aws route53 change-resource-record-sets --hosted-zone-id xxxxxxxxxxxxxx --change-batch file://elb.json
# the command to switch to standard site
aws route53 change-resource-record-sets --hosted-zone-id xxxxxxxxxxxxxx --change-batch file://live.json
```

elb.json = points to AWS ELB (elastic load balancer)

```
{
   "Comment": "back to elb",
   "Changes": [
      {
         "Action": "UPSERT",
         "ResourceRecordSet": {
            "Name": "yourdomain.com",
            "Type": "A",
            "AliasTarget": {
               "HostedZoneId": "xxxxxxxxxxxxxx",
               "EvaluateTargetHealth": false,
               "DNSName": "xxxxxxxxxxxxx.us-east-1.elb.amazonaws.com."
            }
         }
      }
   ]
}
```

live.json = points to your standard site. Value is your IP Address.

```
{
   "Comment": "back to live",
   "Changes": [
      {
         "Action": "UPSERT",
         "ResourceRecordSet": {
            "Name": "yourdomain.com",
            "Type": "A",
            "TTL": 60,
            "ResourceRecords": [
               {
                  "Value": "xxx.xxx.xxx.xxx"
               }
            ]
         }
      }
   ]
}
```