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

- Sign up for Mircosoft Azure
- Logging in
- Creating a Virutal Machine
- Install OSticket on the VM
- Setup OSticket

<h2>Installation Steps</h2>


The first thing you need to do is go to azure.mircosoft.com and sign up for an Mircosoft Azure account. One helpful tip is to sign up for an account. They start you with 200 Azure credits; you can use those instead of using your money until the credits have run out or it has been 30 days.
</p>
<br />

![image](https://github.com/user-attachments/assets/2fcdd9b8-0b81-4636-8eb6-7ff3e6031dad)

After you have signed up for it and then through the steps, you can now log in by going to portal.azure.com, and you will be at your home page.
</p>
<br />

![Screenshot 2025-02-24 175036](https://github.com/user-attachments/assets/f3f110cd-c226-47e5-a141-701526ba5005)


Now that you are on the home page what you do now is go to the top where it says Virtual Machines and click on that link. After that, you would set up for it to be on Windows 10 from the dropbox and make sure you have at least 2-4 vcpu so the VM is not slow. Then click on the bottom link until you create your new VM. Don't forget to click the box that talks about licensing. It may take a few minutes for Azure to prepare and create everything; just be patient. 
</p>
<br />

![image](https://github.com/user-attachments/assets/8e90e95e-ca31-4b0d-8244-312e72a5b735)


In order to use your newly created Virtual Machine, you will have to remote in through the computer you are currently using. If you are on Windows, go to your search bar and type remote desktop connection. A window should come up for you and then go back to your azure account and click on the VM you just created to get your public IP address which is what will be used to remote into the VM. Use the username and password you created for the VM. 
</p>
<br />

![image](https://github.com/user-attachments/assets/1a11651b-74c3-4f7e-926e-025ed7556ca9)


Go to Control Panel > Programs> IIS and check the boxes web management, www services, and application development features
Common HTTP Features, Health and Diagnostics, Performance Features, and Security
CGI 
World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Under Common HTTP Features check
Default Document, Directory Browsing, HTTP Errors, Static Content, HTTP Redirection, WebDAV Publishing

AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console


From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
!! ATTENTION !!
If this appears, choose to “Keep” the file:



If you are still having trouble downloading PHP 7.3.8, please try downloading and installing Google Chrome and doing it from there. 

From the Installation Files, download and install VC_redist.x86.exe.

From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1

Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy the “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, and observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the Installation Files, download and install HeidiSQL.
Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”

Continue setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 

</p>
<br />
