---
title: "Automatically trigger Relay" 
chapter: true
weight: 63
---

# Automatically trigger Relay

14. <a name="ex-step-14"></a>Switch to Relay to observe workflow trigger
  - Click on name of previously imported workflow
  - May currently be labled as **RUNNING**
![Step 14](/images/40_Exercise/14_relay_select_workflow.png)

15. <a name="ex-step-15"></a>Examine steps to see where workflow exits
  - Each time Puppet runs, it sends those previously observed events to the PE server, which forwards them off to any number of configured endpoints for additional processing and storage
  - Some instances of the workflow have probably already ran, the PE server is also managed by Puppet and been forwarding events
  - Click into the most recent run
  - Workflow will exit success but report a number of steps skipped
![Step 15](/images/40_Exercise/15_relay_no_changes_run.png)

16. <a name="ex-step-16"></a>Verify that no corrective changes were detected by examining step logs
  - Click on **View logs** of the **detect-changes** step
![Step 16](/images/40_Exercise/16_relay_no_changes_log.png)

17. <a name="ex-step-17"></a>Make a change to the EC2 instance's sudo configuration out of band of Puppet
  - Removing a file within the `/etc/sudoers.d` directory is sufficient
  - `sudo -i rm /etc/sudoers.d/10_puppetadmin`
![Step 17](/images/40_Exercise/17_rm_sudo_run_puppet.png)

18. <a name="ex-step-18"></a>Re-run Puppet to trigger a corrective change
  - `sudo -i puppet agent -t`
  - Output will again report events related to **Sudo::Conf** but this time you can see that they are tagged **corrective**
![Step 18](/images/40_Exercise/18_puppet_run_corrective.png)

19. <a name="ex-step-19"></a>Return to Relay again to witness the post corrective change workflow run
  - Another instance of the workflow should now be running
![Step 19](/images/40_Exercise/19_relay_changes_run.png)

20. <a name="ex-step-20"></a>Approve instance shutdown action
  - Having detected corrective changes, the workflow will eventually pause at step **Approval required**
  - This approval could be replaced with another mechanism or augmented by a chatops step to prevent having to check in on these runs periodically
  - Click on **Approve**
![Step 20](/images/40_Exercise/20_relay_approve_stop.png)

21. <a name="ex-step-21"></a>Once complete, verify which instance ID was shutdown by Relay
  - When the **ec2-stop-instances** step in complete, open its logs to see the ID of the instance it stopped
![Step 21](/images/40_Exercise/21_relay_stop_log.png)

22. <a name="ex-step-22"></a>Once shutdown, your SSH connection will also be terminated
  - When you return to your EC2 instance's SSH connection, it'll also now be terminated
![Step 22](/images/40_Exercise/22_puppet_cli_instances_stopped.png)