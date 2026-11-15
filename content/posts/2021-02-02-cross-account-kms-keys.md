---
title: 'cross account kms keys'
author: ulysses

date: 2021-02-02
slug: cross-account-kms-keys
draft: false
---

If you have multiple AWS accounts, you can setup a customer-managed KMS (key management service) in the AWS Key Management Service, to secure requests or services between the two AWS accounts. The customer-managed KMS key is tied to an identity such as an IAM user or role. In addition to users and roles, other AWS accounts can be added to grant access. KMS can be symmetric or asymmetric. It’s symmetric be default. To grant access to the other account, you need to add the AWS Account Id to the key. It’s 12 digit number unique to each AWS account.

![](https://uly.me/wp-content/uploads/2021/02/kms-accounts.png)

![](https://uly.me/wp-content/uploads/2021/02/kms-accounts.png)

Once a key is created, the valid key ID can be used in a AWS SDK to access resources from the other AWS account.