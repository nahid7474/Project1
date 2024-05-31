Summary of this project:
----------------------------------------------------------------------------------------------------------------------
This lab project focuses on building a security monitoring environment using Splunk Enterprise Security, with data collected from virtual machines via Universal Forwarder, and specific detection rules established to identify potentially suspicious activities such as Wireshark installation on the network.
I have followed below steps to achieve this goal. 
----------------------------------------------------------------------------------------------------------------------------------------------------
At first, I installed Oracle virtualBox, and couple of virtual machines on it.

<img src="https://github.com/nahid7474/Photos/blob/main/Oracle%20Virtualbox.png"/> 

Went to the Splunk website and download the Splunk Enterprise Security package on one of my windows Virtual machine.
Followed the installation instructions provided by Splunk for my windows operating system and installed Splunk.
<img src="https://github.com/nahid7474/Photos/blob/main/splunk.png"/>

Created my admin credential for first time login as an admin.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk2.png"/>

Opened my web browser and navigate to the Splunk web interface (basically at my localhost:8000).
Logged in with my admin credentials.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk3.png"/>

Created/Configured a few Indexes where I can store my data. I have done this by going to Settings > Indexes in the Splunk web interface.
And then ingested some practice data to make sure it data ingestion is successful (which it is!)

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk11.png"/>

Tested ingested data and they showed up as expected.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk13.png"/>


The next step is to install and Configure Universal Forwarder on a machine from which I want to collect data.
I went to the Splunk website and download the Universal Forwarder package for my 64 bit operating system.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk14.png"/>

Followed the installation instructions and responded to the prompts to configure settings such as the Splunk Enterprise Security instance to forward data to.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk15.png"/>

And then completed the installation process.
At this stage, I also configured data inputs on the Universal Forwarder to collect and forward data to Splunk. 
This includes logs from various Windows Events such as application logs, system logs, security logs etc.

<img src="https://github.com/nahid7474/Photos/blob/main/Splunk16.png"/>
<img src="https://github.com/nahid7474/Photos/blob/main/Splunk15.png"/>

Create Detection Rules:

Now that I have the forwarder installed and configured, It's time for creating detection rules based on the data I am getting. 
In this case, I will install Wireshark and check if my activity is being picked up by Splunk and create a detection rule so next tieme anyone opens wireshark in the environment, I get an alert on that. 




Test Detection Rule:

Run test scenarios or use sample data to ensure that your detection rules are working as expected.
Verify that alerts are triggered correctly for the defined conditions.

Installed Oracle virtualBox, and then windows virtual machines on it. 
 
1. Took snapshots and restore points for each VM. 
 
3. Made sure all VMs are sandboxed/separate from my home network by NAT and they talk to each other
 
 
 
Made sure ciomputers are talking to each other in the virtualized network
 

Install and configurenSplunk Enterprise Security as a SIEM on windows machine.
 
Created admin account and logged in with the admin credentials.
 
Log in as admin and start adding/ingesting data in different ways available
 
Add data source and start ingesting data through monitoring 
 

In this case, I would choose LocalEventLogs and then select application, security and system logs to work on.
 
Kept everything in the main/default index, once configured, Splunk is ready for searching logs
 
Run this test command in the search bar to see if data is searchable, if it is, it indicates that Splunk is configured successfully to receive logs, and ready for the next stage.
 
Define use case, Create correlation search and similate detection

----

Intall and configure Sysmon. Download Sysmon and it’s config file from GitHub. Used powershell with administrator privilege to install Sysmon from the same directory. 
 
 

 
Confirmed from the services that sysmon monitoring service is up and running
 
Malware analysis on Kali Linux using NMAP
Log onto Kali machine and find out the IP address of this machine via ifconfig command in the terminal (10.0.2.15 in this case)
 
To see all the available commands/options NMAP can do, type in nmap -H and this will show a screen below. I will focus on NMAP -A command which will essentially start scanning my target machine which is 10.0.2.15
 
Get more apps
 
 
 
 
Now I will upload more data that are searchable within the Splunk environment and then later be used for detection and correlation purposes. 
Now I will add some more data to enrich my splunk database for better detections. Will do this by uploading a bunch of web and security related traffic, create 2 new indexes named web and security and put everything in there.
 
 
 
 
Configure splunk to listen on port 99777
Download and Install Universal forwarder
Forwarding Windows Event Logs to Splunk Using Universal Forwarder

       
Want to detect any installation task, wireshrk in this case.


Usecase for detection: I want to monitor if any machine in the network is running any application out of the organization’s company portal. This example use case will include our target app “Wireskark”
   
   
 
