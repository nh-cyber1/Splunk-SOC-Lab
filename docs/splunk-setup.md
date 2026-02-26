#Downloaded Ubuntu 24.04.4 iso and created new VM with VMware Workstation Pro


#Installed splunk using terminal and created splunk user.
wget -O splunk-10.2.0-d749cb17ea65-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/10.2.0/linux/splunk-10.2.0-d749cb17ea65-linux-amd64.deb"

sudo /opt/splunk/bin/splunk enable boot-start -user splunk
to run Splunk on startup

Current config for inputs.conf:

[default]
host = Windows11-Victim

[WinEventLog://System]
disabled = 0
index = main

[WinEventLog://Microsoft-Windows-Sysmon/Operational]
disabled = 0
index = main
renderXml = 1

[WinEventLog://Security]
disabled = 0
index = main

whitelist = 4625

[WinEventLog://Microsoft-Windows-Windows Defender/Operational]
disabled = 0
index = main
