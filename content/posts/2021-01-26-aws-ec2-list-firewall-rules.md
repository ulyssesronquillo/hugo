---
title: 'aws ec2 list firewall rules'
author: ulysses

date: 2021-01-26
slug: aws-ec2-list-firewall-rules
draft: false
---

AWS EC2 Firewall rules are defined within security groups. Security groups are attached to an instance. An instance can have up to 5 security groups. Essentially, this script gathers all the security groups associated with an instance, loops through them, and then outputs the ingress and egress rules of each security group to a file in a text format.

```
#!/bin/bash
# set variables
instanceid='i-xxxxxxxxxxxxxxxx'
region='us-east-1'
profile='sample'
# log and temp files
output="ec2-sg.log"
tmpfil="ec2-sg.tmp"
# empty log at start
> $output
# get sg ids
aws ec2 describe-instances \
--instance-ids $instanceid \
--region $region \
--profile $profile \
--query 'Reservations[*].Instances[*].SecurityGroups[*].[GroupId]' --output text > $tmpfil
while read -r id; do
  echo '============================================' >> $output
  echo $id >> $output
  echo '============================================' >> $output
  echo '---------------- INGRESS -------------------' >> $output
  aws ec2 describe-security-groups \
  --group-ids $id \
  --profile $profile \
  --region $region \
  --output text \
  --query 'SecurityGroups[].IpPermissions[].[FromPort,ToPort,IpProtocol,IpRanges[].CidrIp[]|[0]]' >> $output
  echo '---------------- EGRESS --------------------' >> $output
  aws ec2 describe-security-groups \
  --group-ids $id \
  --profile $profile \
  --region $region \
  --output text \
  --query 'SecurityGroups[].IpPermissionsEgress[].[FromPort,ToPort,IpProtocol,IpRanges[].CidrIp[]|[0]]' >> $output
done 
```


Here's a sample output.


```
============================================
sg-xxxxxxxxxxxxxxx
============================================
---------------- INGRESS -------------------
5985    5985    tcp     10.0.0.220/32
10005   10005   tcp     10.0.0.164/32
---------------- EGRESS --------------------
80      80      tcp     10.0.0.14/32
40000   65535   udp     10.0.0.0/8
3389    3389    tcp     10.0.0.96/32
9389    9389    tcp     10.0.0.0/8
5985    5986    tcp     10.0.0.96/32
```