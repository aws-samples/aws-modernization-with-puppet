---
title: "6. Obtaining Access Key"
chapter: true
weight: 20
---

## How to get your access key
Access keys are another set of credentials, similar to EC Key Pairs. However, these credentials allow someone to gain the same permissions as the user that the access key belongs to. In this case, if your user has administrative privileges, that means the access keys can be used to perform almost any actions within your AWS account! We highly recommend reading [the security best practices documentation for access keys](https://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html). 

1. To get your access keys, please go to your IAM dashboard.
1. Select the same user that you created earlier in this section.
1. CLick the security credentials tab.
    ![Security Credentials Page](/images/security-cred.png)
1. Click the **Create access key** button.
1. This will generate a new and active Access Key ID + Secret Access key. Make sure you copy and save the ID in a safe place, as the Secret Access key won't be revealed again.
