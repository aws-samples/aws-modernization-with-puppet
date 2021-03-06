---
title: "3. Marketplace Trial Sign Up"
chapter: true
weight: 11
---
## Signing up for Puppet Enterprise via AWS Marketplace
1. Visit [Puppet Enterprise in AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-df2wt3ipoydbe?trk=el_a134p000003yrYeAAI&trkCampaign=AWSMP_pdp_dev_x_dg&sc_channel=el&sc_campaign=el_awsmp_mult&sc_outcome=Marketplace)
1. You'll land here ![Puppet Enterprise Marketplace](/images/marketplace-page.png)
1. Click the **Continue to Subscribe** button on the top right-hand corner.
1. You may be prompted to sign in to the AWS account you just created, or the one you will be using for this workshop: ![AWS Signup](/images/aws-signin.png)
1. Your page should look like this, notice that the BYOL license doesn't cost anything for the listed instance type: ![Contract Config](/images/mp-contract-config.png)
1. Click the **Accept Terms** button.
1. You have successfully subscribed for Puppet! ![Contract Success](/images/contract-success.png)
1. Click the **Continue to Configuration** button, and you'll land here:
   ![Puppet Software Configuration](/images/byol-configure.png)
1. Once you've filled out the details, go to your ![Launch Config Page](/images/launch-config.png)
1. For the launch configurations, please set the following fields with the following values:
   * Change the EC2 Instance Type to t3.large
   * Leave the VPC settings as your default (when you provision a new AWS account, you'll have a default VPC)
   * Leave the subnet setting as default (this can be a random AZ within the region your management console is currently in)
   * For the Security Group Settings, click the **Create New Based on Seller Settings**
      1. Name your security group ``puppet-workshop-sg``
      1. For the description, write ``SG for Puppet Enteprise``
      1. Click the **Save** button
   * For the Key Pair Setting, select the key pair you created in the previous section.
1. Click the **Launch** button
    ![Launch success](/images/success-launch.png)

And that's it! You have launched a Puppet AMI as an EC2 instance! Click the next button to proceed with requesting AWS credits so this workshop will be **FREE**. 