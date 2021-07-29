---
title: "5. Configure workshop specific requirements"
chapter: true
weight: 18
---

## Configure Additional requirements

1. Deploy one additional EC2 instance to the same region and VPC as where you deployed Puppet Enterprise from the Marketplace
  * Deployment into the same region and VPC is assumed in the workshop instructions and for demonstration purposes, simpler
  * The operating system used for the additional instance during workshop development was CentOS 7, Amazon Linux 2 should also work
  * An instance type of t3.small is sufficient.

2. You are also required to sign up for Relay by Puppet to complete this workshop
  * Visit https://app.relay.sh/signup
  * Provide an email address and password
  * Agree to Terms of Service
  * Click on **SIGN UP**
![Step 2](/images/020_self_guided_setup/02_relay_signup.png)

3. New accounts will look similar to this after you're automatically logged in after account creation
![Step 3](/images/020_self_guided_setup/03_relay_new.png)