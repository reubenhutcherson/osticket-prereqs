<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure
- Virtual Machine
- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

<h3>Step 1: Connect to your Virtual Machine with Remote Desktop</h3>

- If you need help connecting to your virtual machine, please see my tutorial [here](https://github.com/reubenhutcherson/azurevirtualmachine)

<h3>Step 2: Install / Enable Internet Information Services (IIS) in Windows</h3>

- At the bottom left, search control panel.
- Select uninstall a program underneath programs.
- On the left side, select Turn Windows features on or off
- Select Internet Information Services -> World Wide Web Services -> Application Development Features -> [X] CGI and select OK

<p align="center">
<img src="https://i.imgur.com/p74qvZv.jpg" height="80%" width="80%" alt="Azure Free Account"/> 
</p>


<h3>Step 3:  Download and install osTicket Installation Files</h3>

  We will use the files shown below to install osTicket and some of the dependencies. Click here to open: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
 
 <p align="center">
<img src="https://i.imgur.com/vult55A.jpg" height="80%" width="80%" alt="Azure Free Account"/> 
</p>
 
 - From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
 - From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
 - Open File Explorer -> Click on WIndows(C:) -> Create file labeled "PHP"
 
  <p align="center">
<img src="https://i.imgur.com/5qI9LME.jpg" height="80%" width="80%" alt="Azure Free Account"/> 
</p>

- From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- From the Installation Files, download and install VC_redist.x86.exe.
- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  - Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration
  - For the password, we will go with something simple, "Password1"

<p align="center">
<img src="https://i.imgur.com/XfOZiq4.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/gBnXzLc.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/JvtY4J8.jpg" height="80%" width="80%" alt="Azure Free Account"/>  
</p>

<h3>Step 4:  Register PHP from within IIS</h3>
  
  - Search "Windows IIS" -> Open as as administrator by right clicking
  - Select PHP Manager in IIS Manager -> Register new PHP version -> Select php-cgi to execute from Windows(C:)>PHP 
  - Restart IIS Manager
  
  <img src="https://i.imgur.com/5xGrwle.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/hCgmVrx.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/1NbiOc2.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/4XK57ZN.jpg" height="80%" width="80%" alt="Azure Free Account"/>  
</p>  
</p>

<h3>Step 5: Install osTicket</h3>

- Download osTicket v1.15.8 from the Installation Files Folder
- Open downloaded zip file osTicket v1.15.8 -> extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

  <img src="https://i.imgur.com/whFqpEl.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/zWmaX33.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/SpkqDnn.jpg" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 6:Enable PHP Extensions and Assign Permissions</h3>
  
  - Open IIS -> Restart IIS
  - Go to sites -> Default -> osTicket on the right, click “Browse *:80”

 <p align="center">
<img src="https://i.imgur.com/4XK57ZN.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/yAktaKM.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/cUBZn1z.jpg" height="80%" width="80%" alt="Azure Free Account"/> 
</p> 
</p>


 
 
 <h3>Notice that some extensions listed on the page are not enabled.</h3>
      
<img src="https://i.imgur.com/IxxYATm.jpg" height="80%" width="80%" alt="Azure Free Account"/>

- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
  - Enable: php_imap.dll
  - Enable: php_intl.dll
  - Enable: php_opcache.dll
- Refresh the osTicket site in your browser, observe the changes. 
(PHP IMAP Extension and Intl Extension should have green check marks by them)

<p align="center">
<img src="https://i.imgur.com/BMqBvVz.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/cqcOJQD.jpg" height="80%" width="80%" alt="Azure Free Account"/><img src="https://i.imgur.com/hRWU7r5.jpg" height="80%" width="80%" alt="Azure Free Account"/>
</p> 

 
 

