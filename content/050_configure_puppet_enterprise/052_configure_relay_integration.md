---
title: "Configure Relay Integration" 
chapter: true
weight: 52
---

### Configure Relay Integration

Now that we have Puppet code which is capable of managing various configurations, including Puppet Enterprise itself we'll use it to configure the Relay integration for Puppet Enterprise.

9. <a name="pe-step-9"></a>Import newly available classes introduced by freshly deployed Control Repository
  - Return to the PE console
  - Navigate to the **PE Master** node group
  - Find upon the page **Class definitions updated...** and click upon the **Refresh** link
![Step 9](/images/30_Configure_Puppet_Enterprise/09_pe_import_classses.png)

10. <a name="pe-step-10"></a>Add the **profile::relay** class to our **PE Master** node group
  - Select the **Classes** tab
  - In the **Add new class** field type **profile::relay**, the console will attempt to autocomplete 
  - Click on the **Add class** button
![Step 10](/images/30_Configure_Puppet_Enterprise/10_pe_add_profile_relay.png)

11. <a name="pe-step-11"></a>Provide additional data to the **profile::relay** class
  - Using the parameter drop down, add **trigger_token**
  - Set `trigger_token` to the value of the token you obtained from Relay's **puppet-report** trigger in the [Configuring Relay section, step 8]({{< ref "/040_configure_relay#relay-step-8" >}})
  - Commit 1 change to the **PE Master** node group
![Step 11](/images/30_Configure_Puppet_Enterprise/11_pe_commit_profile_relay.png)

12. <a name="pe-step-12"></a>Puppet agent configuration runs do no require shell access, we'll go ahead and use the PE console to initiate the run this time
  - Scroll to the top of the page and find the **Run** drop down menu
  - Select **Puppet**
![Step 12](/images/30_Configure_Puppet_Enterprise/12_pe_run_puppet_console.png)

13. <a name="pe-step-13"></a>New pane will open where you can modify the list of nodes Puppet will be ran on or change **Run options**
  - Click **Run job** to start running Puppet on our PE deployment
![Step 13](/images/30_Configure_Puppet_Enterprise/13_pe_run_puppet_job.png)

14. <a name="pe-step-14"></a>Wait for Puppet run to finish
  - Page will live update with status of Puppet run, eventually reporting **Succeeded**
  - Click on the date coded link in the **Report** column to get a view of what the Puppet run changed
![Step 14](/images/30_Configure_Puppet_Enterprise/14_pe_run_puppet_success.png)

 15. <a name="pe-step-15"></a>Review the Puppet run report
   - There may be additional changes here but the most important as those related to the configuration of Relay
![Step 15](/images/30_Configure_Puppet_Enterprise/15_pe_run_puppet_report.png)