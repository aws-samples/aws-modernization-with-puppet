---
title: "2. Create EC2 Key Pair"
chapter: true
weight: 10
---

## Creating an EC2 Key Pair
An EC2 Key Pair is a set of security credentials to be able to connect to an EC2 instance. The Key pair consists of a public key and a private key. For this workshop, you will need to create a key pair to be able to SSH into the EC2 instance that is hosting Puppet Enterprise. To learn more about EC2 Key Pairs, please go the [key pair documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html).

1. Go to your AWS Management Console and type in ``EC2`` in the search bar, click the result to head to the EC2 dashboard.
1. On your EC2 Dashboard's left-hand, scroll down to the Network & Security section and click the Key Pairs option.
    ![Keypair Menu](/images/keypair-menu.png)
1. On the top right-hand corner, click the **Create key pair** button.
1. Leave the settings on default: Private key file format as .pem and name the keypair as ``puppet-workshop-keypair``.
    ![Keypair Setup](/images/keypair-setup.png)
1. Click the **Create key pair** button on the bottom right, you will be prompted to download this keypair. Download the file and do not delete it!! You will be using this later.

Let's move to the next section where we'll sign up to use Puppet Enterprise for free and launch the software on an EC2 instance.
