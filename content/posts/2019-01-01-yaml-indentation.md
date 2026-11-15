---
title: 'yaml indentation'
author: ulysses

date: 2019-01-01
slug: yaml-indentation
draft: false
---

JSON and YAML are used in AWS CloudFormation. Some people prefer YAML for its simplicity. It’s easy to read and code. However, YAML has its own little quirks. It relies heavily on indentation for its structure. If you don’t use the proper spaces, it will fail. I ran into an issue when I ran CloudFormation in AWS. The example below display the contents of my userdata.

This piece of code will NOT work in CloudFormation.

```
Fn::Base64: !Sub |
#!/bin/bash -xe
yum update -y
mkdir /data
cd /data
aws s3 cp s3://efs-s3-backup-engine .
sleep 30s
initiate.sh
```

This is valid. It’s all about indentation.

```
Fn::Base64: !Sub |
  #!/bin/bash -xe
  yum update -y
  mkdir /data
  cd /data
  aws s3 cp s3://efs-s3-backup-engine .
  sleep 30s
  initiate.sh
```

By the way, tabs are to be avoided like the plague.