# Creating NAT network 

- From Part 1 diagram, we assigned several IP ranges to our splunk server, Windows server, and others. We will configure NAT on these deivices to assign them the correct addresses according to our diagram.

## Configuring NAT 
- Open Virtual Box, Click on Tools, and choose **NAT Networks** from the right pane, and clcik on Create, as shown below.

<img src="https://i.imgur.com/YaXFuWs.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Refer to the diagram in part 1, our network range is 192.168.10.0/24.
- Click on create, enter the range as shown below and our NAT network name. I chose AD-Project. Hit Apply.

<img src="https://i.imgur.com/YaXFuWs.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Next step would be to head over to our Splunk Server, since we need to change the network setting to  **NAT Network**.
- Choose the Splunk server, followed by settings, Network, and choose **NAT Network** from the drop down as shown below.

<img src="https://i.imgur.com/tvAjKPS.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Do the above step of changing to NAT Network for all your other VMs, that is Windows server, Active Directory, and Kali.
- Start your splunk server.
- Enter the command  **ip a**. We can see the IP address of our splunk, as shown below.

<img src="https://i.imgur.com/XEMnKd2.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
- We will be setting a static IP address, taking the exact IP from our Diagram from Part 1.
