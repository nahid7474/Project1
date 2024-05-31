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

Install Wireshark and detect this activity in Splunk 
---------------------------------------------------------

Now that I have the forwarder installed and configured, It's time  to test that my VM is forwarding logs to Splunk.
In this case,  I will install Wireshark and check if my activity is being picked up by Splunk. 

<img src="https://github.com/nahid7474/Photos/blob/main/wireshark.png"/>
<img src="https://github.com/nahid7474/Photos/blob/main/wiresharkActivity.png"/>

A splunk search shows that this activity has indeed been picked up by Spunk.

<img src="https://github.com/nahid7474/Photos/blob/main/wiresharkDetection.png"/>

Create alert 
----------------------------------------------------------------------
Now that I have detected this activity, I can save this as an alert. 
Essentially, everytime someone installs/opens wireshark this will alert me and send me an email as well with a link to the detection for investigation. 

<img src="https://github.com/nahid7474/Photos/blob/main/DetectionRule.png"/>


   
 
