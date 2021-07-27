---
title: "Enable sudo management" 
chapter: true
weight: 61
---

# Enable sudo management

Assigning a class to new EC2 instances is what enables sudo management. In the control repository we are currently working with for this lab has included the appropriate configurations as part of a class named **profile::base**.

1. <a name="ex-step-1"></a>Navigate the **PE Agent** node group
  - Return to the **Node groups** section of the console
  - Expand **PE Infrastructure**, if still not expanded from previous steps
  - Click on **PE Agent** link
![Step 1](/images/40_Exercise/01_pe_node_group_agent.png)

2. <a name="ex-step-2"></a>Add class **profile::base**
  - The Control Repository we previous deployed contains a class named **profile::base** which will setup sudo management
  - Begin typing **profile::** and the console with autocomplete, select **profile::base** and then click **Add class**
![Step 2](/images/40_Exercise/02_pe_add_profile_base.png)

3. <a name="ex-step-3"></a>Commit chnages to **PE Agent** node group
  - There are no additional pieces of data to set for this class for click on **Commit 1 change**
![Step 3](/images/40_Exercise/03_pe_commit_profile_base.png)