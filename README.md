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
   
   
 
