---
title: "Worflow automation with Relay and Puppet Enterprise" 
chapter: true
weight: 1
---

![Logo](/images/logo-combined.png)

## Workflow automatation with Relay and Puppet Enterprise

### Welcome

An advantage of Infrastructure as Code practices is that once infrastructure and applications are brought under management you are able to track the history of configuration over time and react to unauthorized changes. Puppet Enterprise detects and reports upon these changes, being able to determine when a change initiated by a configuration of the client is intentional or corrective, which has the potential to trigger additional automation to protect you from outage or a security breach. In this workshop we'll dip into the security use case by integrating Puppet Enterprise with Relay, an easy event driven workflow automation solution for cloud operations teams built by Puppet which has direct integration with both Puppet Enterprise and AWS. Through this integration you'll see how unauthorized corrective changes to an EC2 instance's sudo configuration can be acted upon to fence the node, shutting it down, and leaving it for future examination.

<a href="https://aws.amazon.com/marketplace/pp/B07PZY3369?&trk=el_a134p000003yrYeAAI&trkCampaign=AWSMP_pdp_dev_x_dg&sc_channel=el&sc_campaign=el_awsmp_mult&sc_outcome=Marketplace" target="_blank"><img src="/images/setup/available-in-awsmp-badge.png"></a>