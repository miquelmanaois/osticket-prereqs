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
- Item 4
- Item 5

<h2>Installation Steps</h2>


<h3>Step 1: Connect to your Virtual Machine with Remote Desktop</h3>

- If you need help connecting to your virtual machine, please see my tutorial [here](https://github.com/miquelmanaois/virtualmachine)

<h3>Step 2: Install / Enable IIS in Windows</h3>

- At the bottom left, search control panel.
- Select uninstall a program underneath programs.
- On the left side, select Turn Windows features on or off
- Select Internet Information Services, and select OK.


<p align="center">
<img src="https://i.imgur.com/Cxy8NM7.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/f1eRIx4.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>


<h3>Step 3:  Download, install, and open Web Platform Installer. Afterwards, download necessary files
</h3>

- Once Web Platform Installer is open, go to the top right and search MySQL 5.5. 
- Go to MySQL Windows 5.5 and click add. 
- Go again to the top right and search for php.
- Add All simple versions of x86 PHP up until 7.3
- Select install at the bottom and it will tell you to create a username and password      to finish installation
  - Username: root
  - Password: Password1
- You might get a message saying some products have failed to install.
- Download and install the following from within the lab files: link
  - PHP Version 7.3.8
  - PHP Manager 1.5.0 for IIS 10
  - Microsoft Visual C++ 2009 Redistributable Package


<p align="center">
<img src="https://i.imgur.com/Ed9wc2j.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/7ryNBQg.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>


<h3>Step 4: Install osTicket v1.15.8</h3>
     
- Download osTicket (download from within lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6))
- Right click on the file and select extract all
- Copy the “upload” folder INTO c:\inetpub\wwwroot
- Rename “upload” to “osTicket”


<p align="center">
<img src="https://i.imgur.com/QhE5p74.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/I5yvFc4.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>
 
     

<h3>Step 5: Reload IIS (Open IIS, Stop and Start the server)
</h3>

- Search for Internet Information Services (IIS) and select open
- On the left, select Sites -> Default Website -> osTicket
- On the right, click “Browse *:80”
- Before continuing, head back to and open IIS.


<p align="center">
<img src="https://i.imgur.com/nOv1FP1.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 6:  Enable Extensions in IIS: Note that some extensions are not enabled
</h3>

- Go back to IIS, Sites -> Default Web Site -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension” at the bottom under “PHP Extensions”
- Right click and enable the following
    - php_imap.dll
    - php_intl.dll
    - Php_opcache.dll

 
     
 <p align="center">
<img src="https://i.imgur.com/14pPOdv.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/okabWbT.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>

<h3>Step 7:   Refresh the osTicket site in your browser, observe the changes
</h3>

- Intl Extension should now have a green check mark next to it


<p align="center">
<img src="https://i.imgur.com/okabWbT.png" height="60%" width="60%" alt="Azure Free Account"/>



<h3>Step 8: Rename</h3>
 
- Open Windows Explorer and select C:-> inetpub-> wwwroot-> osTicket-> Include and rename.
	- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
	- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php


<p align="center">
<img src="https://i.imgur.com/rEBpL8Y.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 9: Assign Permissions: ost-config.php</h3>

- Right click ost-config.php, 
- Open Properties -> Security -> Advanced -> Permissions 
- Select Disable inheritance -> Remove all inherited permissions from this object 
- Afterwards, Select add ->New Permissions -> Everyone -> All

<p align="center">
<img src="https://i.imgur.com/rEBpL8Y.png" height="80%" width="80%" alt="Azure Free Account"/>
  
<h3>Step 10: Continue Setting up osTicket in the browser</h3>

- Go back to browser and click continue
  - Name: Helpdesk
  - Email: whichever email you want
  
<p align="center">
<img src="https://i.imgur.com/rEBpL8Y.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 11: Download and Install HeidiSQL</h3>

- Open HeidiSQL and create new session
   - User: root
   - Password : Password1
- Select Open
- On the left side, right click “Unamed” -> “Create New” -> “Database
- Name it “osTicket”

 <p align="center">
<img src="https://i.imgur.com/14pPOdv.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/okabWbT.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>

<h3>Step 12:  Go back to the browser and continue setting up osTicket by filling out the fields.</h3>

- First Name: your first name
- Last Name: your last name
- Email Address: whichever email you want (needs to be different from the Default Email)
- Username: user_admin 
- Password: Password1 
- MySQL Database: osTicket (the one you just created in HeidiSQL)
- MySQL Username: root
- MySQL Password: Password1
- Finally, click Install Now

 <p align="center">
<img src="https://i.imgur.com/14pPOdv.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/okabWbT.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>

🎉Congratulations! You have sucessfully installed osTicket!🎉

<h3>Step 13: Cleanup.</h3>

- Go to C: -> inetpub->wwwroot->osTicket->setup
    - Delete the contents in the setup folder
    - Afterwards, delete the setup folder
- Go to C:-->Inetpub-->wwwroot-->osTicket-->include
    - Right click on ost-config.php 
    - Select securities -> Advanced -> edit to change permissions
	- Allow everyone to only have read and execute
	
 <p align="center">
<img src="https://i.imgur.com/14pPOdv.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/okabWbT.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>	



