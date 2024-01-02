<p align="center">
  
![osTicket logo](https://github.com/Kolapo72/installation/assets/147263584/7a82fce3-40e1-4b08-ab51-ccde0b6301f5)
</p>

<h1>Installation</h1>
The installation of osTicket requires some files to install from osTicket and some of the dependencies. Follow the steps accordingly;
  
![IIS Enablw](https://github.com/Kolapo72/installation/assets/147263584/1edff233-51d0-41d9-ac20-b43cc1e774f2)
<h4>Step 1: Install/Enable IIS in Windows With CGI and Common HTTP Features</h4>
<li>World Wide Web Services -> Application Development Features -> [X] CGI   [X] Common HTTP Features and IIS Management Console</li>
<li>Internet Information Services -> Web Management Tools -> IIS Management Console</li>
	[X] IIS Management Console
 
![IIS Activated](https://github.com/Kolapo72/installation/assets/147263584/ac09eee9-fc2e-40b3-b827-0777120d31b9)
 Note: On Browser, check with 127.0.0.1 if IIS is activated.
 
 --------------------------------------------------------------------------------------------------

![PHP Manager](https://github.com/Kolapo72/installation/assets/147263584/3dba1caf-9a2b-48a9-9c23-ac9d9d3537b4)
<h4>Step 2: Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</h4>

---------------------------------------------------------------------------------------------------

![Rewrite module](https://github.com/Kolapo72/installation/assets/147263584/c8b069a9-62ab-4077-a75c-93a26a53b4d5)
<h4>Step 3: Download and install the Rewrite Module (rewrite_amd64_en-US.msi)</h4>

--------------------------------------------------------------------------------------------------

<h4>Step 4: Create the directory C:\PHP</h4>
Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

![PHP Note 1](https://github.com/Kolapo72/installation/assets/147263584/bcd617d6-1fb6-4568-b6f1-556c4f8040ba)
![PHP Note 2](https://github.com/Kolapo72/installation/assets/147263584/3aeacc81-57c6-4df9-a3d4-1159c1fd381e)

<p>Note: If you are still having trouble downloading PHP 7.3.8, please try downloading and installing Google Chrome and doing it from within there.</p>

<h4>Step 5: Download and install VC_redist.x86.exe</h4>

---------------------------------------------------------------------------------------------------
<h4>Step 6: Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)</h4>
<li>Typical Setup</li>
<li>Launch Configuration Wizard (after install)</li>
<li>Standard Configuration</li>
<li>Password1</li>

---------------------------------------------------------------------------------------------------
<h4>Step 7: Open IIS as an Admin</h4>
<li> Register PHP from within IIS</li>
<li>Reload IIS (Open IIS, Stop and Start the server)</li>

----------------------------------------------------------------------------------------------------
<h4>Step 8: Install osTicket v1.15.8</h4>
  <li>Download osTicket from the Installation Files Folder</li>
  <li>Extract and copy “upload” folder to c:\inetpub\wwwroot</li>
  <li>Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</li>

----------------------------------------------------------------------------------------------------
<h4>Step 9: Reload IIS (Open IIS, Stop and Start the server)</h4>
Go to sites -> Default -> osTicket
  <ul>On the right, click “Browse *:80”</ul>

Note that some extensions are not enabled
-	Go back to IIS, sites -> Default -> osTicket
-	Double-click PHP Manager
-	Click “Enable or disable an extension”
-	Enable: php_imap.dll
-	Enable: php_intl.dll
-	Enable: php_opcache.dll
-	Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php
-	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
-	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
-	Disable inheritance -> Remove All
-	New Permissions -> Everyone -> All

---------------------------------------------------------------------------------------------------
<h4>Step 10: Continue Setting up osTicket in the browser (click Continue)</h4>
<li>Name Helpdesk</li>
<li>Default email (receives email from customers)</li>

---------------------------------------------------------------------------------------------------
<h4>Step 11: From the Installation Files, download and install HeidiSQL.</h4>
<li>Open Heidi SQL</li>
<li>Create a new session, root/Password1</li>
<li>Connect to the session</li>
<li>Create a database called “osTicket”</li>

---------------------------------------------------------------------------------------------------
<h4>Step 12: Continue Setting up osticket in the browser</h4>
<ul>MySQL Database: osTicket</ul>
<ul>MySQL Username: root</ul>
<ul>MySQL Password: Password1</ul>
<ul>Click “Install Now!”</ul>

<h4>Congratulations, hopefully it is installed with no errors!</h4>
<li>Browse to your help desk login page: http://localhost/osTicket/scp/login.php</li>
<li>End Users osTicket URL:	http://localhost/osTicket/</li>
