<h1>Hi there my name is Brian<h1>
 Step By Step Process To Access OSticket 
 
    

1. Make A Virtual Machine in Azure
2. Select Windows 10
3. Make username and password that is easy to remember for further usage 
4. Copy and paste the IP Address to access and start the usage of Virtual Machine 
5. While operating the vm change all of the settings to no.
6. Next, go into settings on the windows browser to open the installation files
7. Install and Enable IIS in windows with CGI and Common HTTP features: 		World Wide Web Services -> Application Development Features -CGI Common HTTP Features. Internet Information Services -> Web Management Tools -> IIS Management Console
8. Next up, go installation files and download and install PHP Manager and Rewrite Module
  9. Create the directory C:\PHP - From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
10. From the Installation Files, download and install VC_redist.x86.exe.


11. From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1
Open IIS as an Admin
Register PHP from within IIS
Reload IIS (Open IIS, Stop and Start the server)


12. Install osTicket v1.15.8

Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)


Go to sites -> Default -> osTicket

On the right, click “Browse *:80”

Note that some extensions are not enabled

13. Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes

Rename: ost-config.php

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



Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:

http://localhost/osTicket/ 

Part 3 (Post Installation Setup)

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

Part 4 (Tickets and Ticket Lifecycle)

Just practice creating, triaging, and solving tickets. I recommend watching the video to learn about triaging multiple tickets.
Ticket examples:
Sev-A (1 hour, 24/7) [entire mobile/online banking system is down] -> SysAdmins
Sev-B (4 hours, 24/7) [accounting department needs adobe upgrade, broken]
Sev-B/C (2 hours, business hours) [CFO’s laptop seems a bit slow]
