#Downloaded Ubuntu 24.04.4 iso and created new VM with VMware Workstation Pro
#Installed splunk using terminal and created splunk user.
wget -O splunk-10.2.0-d749cb17ea65-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/10.2.0/linux/splunk-10.2.0-d749cb17ea65-linux-amd64.deb"

sudo /opt/splunk/bin/splunk enable boot-start -user splunk
to run Splunk on startup
