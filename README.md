<h1>Hi there my name is Brian<h1>
 Today I will break down the process of installing and working with OSTicket through a Virtual Machine using Windows 10 
 

Here is a step By Step Process To Access OSticket 
    
1. Make A Virtual Machine in Azure ![image](https://github.com/BrianSpencer23/brianspencer23/assets/139722626/0c944ae8-d78c-4f05-b383-c95d5b94ed38)
2. Select Windows 10
3. Make username and password that is easy to remember for further usage 
4. Copy and paste the IP Address to access and start the usage of Virtual Machine 
5. While operating the vm change all of the settings to no.
6. Next, go into settings on the windows browser to open the installation files
7. Install and Enable IIS in windows with CGI and Common HTTP features: 		World Wide Web Services -> Application Development Features -CGI Common HTTP Features. Internet Information Services -> Web Management Tools -> IIS Management Console <a href="https://imgur.com/GgRBWHG"><img src="https://i.imgur.com/GgRBWHG.png" title="source: imgur.com" /></a>          
8. Next up, go installation files and download and install PHP Manager and Rewrite Module <a href="https://imgur.com/JSfLo1F"><img src="https://i.imgur.com/JSfLo1F.png" title="source: imgur.com" /></a>
  9. Create the directory C:\PHP - From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
10. From the Installation Files, download and install VC_redist.x86.exe. <a href="https://imgur.com/dzgDP14"><img src="https://i.imgur.com/dzgDP14.png" title="source: imgur.com" /></a>


11. From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1
Open IIS as an Admin
Register PHP from within IIS
Reload IIS (Open IIS, Stop and Start the server)
<a href="https://imgur.com/lKorgH8"><img src="https://i.imgur.com/lKorgH8.png" title="source: imgur.com" /></a>

12. Install osTicket v1.15.8

Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)<a href="https://imgur.com/aKKEtZG"><img src="https://i.imgur.com/aKKEtZG.png" title="source: imgur.com" /></a>


Go to sites -> Default -> osTicket <a href="https://imgur.com/dWeWz6W"><img src="https://i.imgur.com/dWeWz6W.png" title="source: imgur.com" /></a>

On the right, click “Browse *:80”

Note that some extensions are not enabled

13. Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php <a href="https://imgur.com/yzG1y4K"><img src="https://i.imgur.com/yzG1y4K.png" title="source: imgur.com" /></a>

From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php

Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)

Name Helpdesk
Default email (receives email from customers)

From the Installation Files, download and install HeidiSQL.

Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”

Continue Setting up osticket in the browser
Example:
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”
<a href="https://imgur.com/aTwn5A6"><img src="https://i.imgur.com/aTwn5A6.png" title="source: imgur.com" /></a>


Browse to your help desk login page: http://localhost/osTicket/scp/login.php <a href="https://imgur.com/Ol4BJxD"><img src="https://i.imgur.com/Ol4BJxD.png" title="source: imgur.com" /></a>

End Users osTicket URL:

http://localhost/osTicket/ 

Part 3 (Post Installation Setup)

Next Steps: Here we have the process of the daily task of working with OSTicket.
<a href="https://imgur.com/6ffBpHX"><img src="https://i.imgur.com/6ffBpHX.png" title="source: imgur.com" /></a>
Follow these next steps:
Configure Roles
Admin Panel -> Agents -> Roles
Supreme Admin
Configure Departments
Admin Panel -> Agents -> Departments
System Administrators
Configure Teams
Admin Panel -> Agents -> Teams
Level I Support
Level II Support
Allow anyone to create tickets
Admin Panel -> Settings -> User Settings
Registration Required: Require registration and login to create tickets
Configure Agents (workers)
Admin Panel -> Agents -> Add New
Jane
John
Configure Users (customers)
Agent Panel -> Users -> Add New
Karen
Ken
Configure SLA
Admin Panel -> Manage -> SLA
Sev-A (1 hour, 24/7)
Sev-B (4 hours, 24/7)
Sev-C (8 hours, business hours)
Configure Help Topics
Admin Panel -> Manage -> Help Topics
Business Critical Outage
Personal Computer Issues
Equipment Request
Password Reset

Part 4 (Tickets and Ticket Lifecycle) <a href="https://imgur.com/6XwdqjJ"><img src="https://i.imgur.com/6XwdqjJ.png" title="source: imgur.com" /></a>


Ticket examples as shown: <a href="https://imgur.com/6ffBpHX"><img src="https://i.imgur.com/6ffBpHX.png" title="source: imgur.com" /></a>
Sev-A (1 hour, 24/7) [entire mobile/online banking system is down] -> SysAdmins
Sev-B (4 hours, 24/7) [accounting department needs adobe upgrade, broken]
Sev-B/C (2 hours, business hours) [CFO’s laptop seems a bit slow]


With repeating this whole  process you can be sure to find it to be easy the more times you do the tasks that are provided. 

[linkedin]: https://www.linkedin.com/in/brian-spencer-740b93227/
