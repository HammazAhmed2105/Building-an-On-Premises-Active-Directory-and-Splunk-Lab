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

# -----

## Setting up Splunks IP

- Start your splunk server.
- Enter the command  **ip a**. We can see the IP address of our splunk, as shown below.

<img src="https://i.imgur.com/XEMnKd2.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
- We will be setting a static IP address, taking the exact IP from our Diagram from Part 1, that is 192.168.10.10
- Enter the below command-
- **NOTE** - Press tab after typing **netplan/**. This will help you auto complete the next available file.
```Powershell
sudo nano /etc/netplan/
```
- We will be presented with a screen

<img src="https://i.imgur.com/4anTYiO.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Use the arrows on your keyboard to navigate and set up everything as I have shown below.

<img src="https://i.imgur.com/XxRIenX.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- **Note** - Type in nameservers with an s, and not name server.
- To save the config, hit CTRL+X, you will be prompted with a confirmation, enter Y, and hit Enter.
- To appy the configurations enter the command
```powershell
sudo netplan apply
```
- Enter **ip a** again to check the ip address and it should be changed to 192.168.10.10
<img src="https://i.imgur.com/B6NKPJr.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

# -----

## Installing Splunk

- Head over the Splunk.com, and register with your email id. Click on Products, followed by Free Trials & Downloads.

<img src="https://i.imgur.com/8J6huI2.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Look for the Splunk Enterprise version, and hit **Get my free Trial**.
- Register with your details.
- Once you're shown the below screen, click on Linux and download the **.deb** file.

<img src="https://i.imgur.com/jeWrQ6Y.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

### Installing Guest Ad-ons on our Splunk VM.
- Type in the below command
```powershell
sudo apt-get install virtualbox-guest-additions-iso
```
- Once the installation is done, head over to Devices, Shared folder, and click on Shared fodler settings, as shown below.

<img src="https://i.imgur.com/FnDrPNX.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Right click on the "Plus" icon, and as for the folder path, choose wehre you saved your splunk instance. Check the box for Read-Only and Auto mount.
<img src="https://i.imgur.com/rb8huJn.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Head back to your splunk CLI, and enter "sudo reboot".
  
## Adding user to the VBoxsf group.

- Use the command below to download guest-utils
```powershell
sudo apt-get install virtualbox-guest-utils
```
- reboot using "sudo reboot"
- Now to add our user, for me its "hammaz", we use the below command.
```powershell
sudo adduser hammaz vboxsf
```
<img src="https://i.imgur.com/Q5L4tfE.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- create a new directory by typing "mkdir share"
- type "exit", and log back in. This will make sure out added user has taken effect.
## Mounting our shared folder of Active directory to this nely created "share" folder.

```powershell
sudo mount -t vboxsf -o uid=1000,gid=1000 AD-Project share/
```
- Make sure you use the folder name of "AD-Project" according to what name you have. If you want to double check, go to devices, and clikc shared folder settings as shown belo.

<img src="https://i.imgur.com/E8fZhJu.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
- I used cd and ls to change and list the contents of my share folder. As shown below, we succesfully mounted everything.

<img src="https://i.imgur.com/jL1zdjt.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

## Installing Splunk
```powershell
sudo dpkg -i splunk
```
- after typing splunk in the above command, hit enter to autofill.
<img src="https://i.imgur.com/Zm2ANUD.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Give it sometime and splunk will be installed.
- Once done, it will show "complete" to indicate splunk has been correctly installed.

## Running the splunk Installer
- Splunk is located in the opt folder. we can use cd to change into the splunk folder.
```powershell
cd /opt/splunk
```
- to change to the user as splunk we use
```powershell
sudo -u splunk bash
```
- change the to bin directory and start splunk
```powershell
cd bin
./ splunk start
```
<img src="https://i.imgur.com/6xukzV5.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
- Keep hitting space to read or skip the terms and condition, and then choose a username and password of your choice.
- Once we are shown the below screen, the installtion is done.

<img src="https://i.imgur.com/sEvcGF6.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
- If you want that splunk starts everytime your virtual machine reboots, use the below commands.

```powershell
exit
cd bin
sudo ./splunk enable boot-start -user splunk
```
<img src="https://i.imgur.com/sEvcGF6.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

# Setting up Splunk Forwarder and Sysmon on our target machine












