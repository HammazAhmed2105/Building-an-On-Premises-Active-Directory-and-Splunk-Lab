# Creating NAT network 

- From Part 1 diagram, we assigned several IP ranges to our splunk server, Windows server, and others. We will configure NAT on these deivices to assign them the correct addresses according to our diagram.

## Configuring NAT 
- Open Virtual Box, Click on Tools, and choose **NAT Networks** from the right pane, and clcik on Create, as shown below.

<img src="https://i.imgur.com/YaXFuWs.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Refer to the diagram in part 1, our network range is 192.168.10.0/24.
- Once you click on create, enter the range as shown below and our NAT network name. I chose AD-Project. Hit Apply.

<img src="https://i.imgur.com/YaXFuWs.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
