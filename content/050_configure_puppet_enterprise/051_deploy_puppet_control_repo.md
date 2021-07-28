---
title: "Deploy Puppet Control Repository" 
chapter: true
weight: 51
---

### Configure Puppet Control Repsitory

The first step in setting up a new Puppet Enterprise deployment is importing a control repository, which contains the Puppet code which is used to define the configurtion of managed resources.

**Before you get started ensure that Puppet Enterprise has completed its post deployment configuration process!** The steps for ensuring setup are complete are documented [here](https://puppet.com/docs/pe/2019.8/cloud_installing.html#aws-install) on the Puppet documentation website.

1. <a name="pe-step-1"></a>Navigate to the Puppet Enterprise console, which runs over the standard HTTPS port (443)
  - Find and click on **Node groups**, found in the left side navigation panel
![Step 1](/images/30_Configure_Puppet_Enterprise/01_pe_node_groups.png)

2. <a name="pe-step-2"></a>Expand **PE Infrastructure** and click on **PE Master**
![Step 2](/images/30_Configure_Puppet_Enterprise/02_pe_node_groups_pe_master.png)

3. <a name="pe-step-3"></a>Click on **Classes**, found in the horizontal set of tabs
![Step 3](/images/30_Configure_Puppet_Enterprise/03_pe_master_classes_tab.png)

4. <a name="pe-step-4"></a>Scroll down until you find **Class: puppet_enterprise::profile::master**
  - Use the drop down menu **Parameter Name** and find **r10k_remote**
  - Set **r10k_remote** to `https://github.com/puppetlabs/aws-hol-repo.git` and click **Add to node group**
  - Now set **code_manager_auto_configure** to `true`
  - Commit changes by clicking on **Commit 2 changes**
![Step 4](/images/30_Configure_Puppet_Enterprise/04_pe_master_code_manager_config.png)

5. <a name="pe-step-5"></a>Log into your PE deployment as `puppetadmin` via SSH and run Puppet via the CLI
  - `sudo -i puppet agent -t`
![Step 5](/images/30_Configure_Puppet_Enterprise/05_pe_run_puppet_cli.png)

6. <a name="pe-step-6"></a>Once you see similar output and you're returned to a command prompt then continue to the next step
![Step 6](/images/30_Configure_Puppet_Enterprise/06_pe_run_puppet_cli_results.png)

7. <a name="pe-step-7"></a>To deploy our Control Repository we first authenticate to the PE API
  - `sudo -i puppet access login --lifetime=1y`
  - Login with credentials set during the AWS Marketplace PE deployment process
![Step 7](/images/30_Configure_Puppet_Enterprise/07_pe_get_access_token.png)

8. <a name="pe-step-8"></a>Deploy the production code environment
  - `sudo -i puppet code deploy production --wait`
![Step 8](/images/30_Configure_Puppet_Enterprise/08_pe_deploy_control_repo.png)