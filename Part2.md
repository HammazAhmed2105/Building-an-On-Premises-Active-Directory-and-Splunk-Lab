# Installing Windows10 on VM, and configuring Splunk Server

### I am using Oracle Virtual Box as my VM.
- I'm not showing the installation of Virtual box since Its simple and I have done it multiple times. I'm providing a tutorial for any beginners who are reading this. https://youtu.be/nvdnQX9UkMY?si=Pv-f6aCohTyT4NCR

# -----

## Installing Windows 10 on VM
- We will use the below link make a Windows ISO image file.
- https://www.microsoft.com/en-ca/software-download/windows10
- Click on download now. This will download "Media Creation Tool".

<img src="https://i.imgur.com/sQ0u5iB.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- Click on the Downloaded file, and click  Accept.

<img src="https://i.imgur.com/7KQv4Ot.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

- As shown below, choose the 2nd option, since we are interested in making our own ISO, and not upgrading our own system.

<img src="https://i.imgur.com/ZKEaGrQ.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Keep the default option for the next step, and then we will be presented with the below options. Choose ISO Image. Choose your preferred location to store this file, and wait till the installation is done.

<img src="https://i.imgur.com/5O1lWxE.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>


# -----

## Installing the Windows 10 ISO on our Virtual Box.

- Now that the download is done we will install the Windows 10 ISO file on our Virtual Box.
- Open Virtual Box, Click on new, select whatever location you want your files to saved in. Also select the ISO image from the appropriate location.
- Make sure you click the "Skip unattended installation", this helps us to install the operating system, manually. Hit next.

<img src="https://i.imgur.com/H1wYsft.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- I'm keeping the memory as 4GB, and 1 core is used. You can definitely increase that according to your own PC.

<img src="https://i.imgur.com/H1wYsft.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Our configuration is done. Click finish.

## Powering on our Windows VM, and configruing it.

- Click on Start to power up our VM.
<img src="https://i.imgur.com/cCWDZSQ.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- We will be shown with the below screen.

<img src="https://i.imgur.com/XJmcI2B.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Click next, Install now, and choose "I don't have a product key" from the bottom pane.
- Choose Windows 10 Pro from the next window.
- In the next screen, choose Custom Installation.
- Click next, and we are done with the windows installation.

# -----

## Installing Windows Server 2022

- Use the given link. https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022
- Click on Download ISO.

<img src="https://i.imgur.com/JNwgVkP.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Fill in the information that's asked in the next page.
- Choose the  64 bit edition as shown below.

<img src="https://i.imgur.com/QX9SJ52.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Once the file is downloaded, open Virtual box, and click on new.  Give a name to your Server, select the storage folder, and select the previously downloaded Server's ISO image.
- Make sure you click **Skip unattended Installation**. Hit Next.

<img src="https://i.imgur.com/Gtcyhlp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- As for the Hardware I chose 4MB, and 1 CPU core, and harddisk as 50 gigs.
- That's all. Hit Finish and Click on Start to boot up your Virtual Server.

<img src="https://i.imgur.com/XjxoEvI.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

- Click on Next, followed by Install now.
- From the below screen, make sure you choose the 2nd option, otherwise you will only get a CLI, and no GUI.

<img src="https://i.imgur.com/sV4GSNx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>










