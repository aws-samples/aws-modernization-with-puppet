---
title: "Corrective Change Exercise" 
chapter: true
weight: 60
---

# Unauthorized changes to sudo exercise

In this lab we'll enroll the additional EC2 instance you deployed while setting up prerequisites into Puppet Enterprise and start managing sudo. When sudo is managed we'll look at how our imported workflow is triggered then make a simple change to the EC2 instance to trigger a corrective change on the next Puppet run. With the sudo configuration successfully remediated, return to Relay one more time and observe the difference between this execution of our workflow vs. the previous envocation.