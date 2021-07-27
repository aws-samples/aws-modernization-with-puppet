---
title: "On-board new EC2 instance" 
chapter: true
weight: 62
---

# On-board new EC2 instance

4. <a name="ex-step-4"></a>Naviage to **Nodes** section via the vertical navigation bar
  - You should only see a single other node currently listed, this is the PE deployment
![Step 4](/images/40_Exercise/04_pe_nodes_section.png)

5. <a name="ex-step-5"></a>Click on the **Add nodes** button
  - Will send you a page which lists a couple ways of adding a node to inventory
![Step 5](/images/40_Exercise/05_pe_add_nodes.png)

6. <a name="ex-step-6"></a>Click on the **Install agents** button
  - Since we're working with EC2 instances, we'll choose **Install agents**
  - Puppet can also manage devices and API endpoints
![Step 6](/images/40_Exercise/06_pe_install_agents.png)

7. <a name="ex-step-7"></a>Copy command for initiating an agent install from the cli
  - To avoid setting up and distributing SSH credentials for our workshop, we'll copy the command for ***nix** under the **Install agents on the command line** section
  - This command could also be integrated into your standard provisioning workflow to ensure Puppet is installed on first boot
![Step 7](/images/40_Exercise/07_pe_copy_installer_cmd.png)

8. <a name="ex-step-8"></a>Run copied command on EC2 instance
  - SSH into the additional EC2 instance that you deployed during prerequisite setup as user **centos**
  - Paste command onto cli
![Step 8](/images/40_Exercise/08_agent_cli_run_installer_cmd.png)

9. <a name="ex-step-9"></a>Run Puppet for the first time, waiting for onboarding approval
  - With Puppet installed, initiate the first configuration run
  - Puppet will wait for you to approve the new node, checking to see if it can continue every 5 seconds
  - `sudo -i puppet agent -t --waitforcert 5`
![Step 9](/images/40_Exercise/09_agent_cli_first_run_wait.png)

10. <a name="ex-step-10"></a>Navigate to **Certificates** section of PE console
  - Return to the PE console and refresh your browser
  - There is now bee the number 1 next to **Certificates** in the vertical navigation bar
![Step 10](/images/40_Exercise/10_pe_certificates_section.png)

11. <a name="ex-step-11"></a>Select **Unsigned Certificates** tab
  - This number 1 will also be present next to **Unsigned Certificates**
  - Click on this tab
![Step 11](/images/40_Exercise/11_pe_new_certificates_tab.png)

12. <a name="ex-step-12"></a>Accept new agent certificate
  - Click on the **Accept** button
![Step 12](/images/40_Exercise/12_pe_accept_agent_cert.png)

13. <a name="ex-step-13"></a>Wait for Puppet to finish its initial run
  - Return to your SSH session and the Puppet run will have started
  - When it finishes you'll likely see events related to **Sudo::Conf**
![Step 13](/images/40_Exercise/13_agent_first_run_complete.png)