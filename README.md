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

- Windows 10 Pro</b> (22H2)

<h2>List of Prerequisites</h2>

- IIS with CGI
- PHP Manager for IIS
- osTicket
- IIS Rewrite Module
- PHP Runtime
- If needed, VC_Redist.x86 Package
- MySQL & HeidiSQL

<h2>Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/TS1zRT1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Search: "Windows features" > Select "Turn Windows features on or off" > Toggle "Internet Information Services", then expand it > In "World Wide Web Services", expand "Application Development Features" and enable "CGI" > Save & close.  
</p>
<br />

<p>
<img src="https://i.imgur.com/4N8sBA5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install BOTH PHP Manager for ISS and Rewrite Module. PHP Manager: https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10 | Rewrite Module: https://www.iis.net/downloads/microsoft/url-rewrite
</p>
<br />

<p>
<img src="https://i.imgur.com/2f7qlw5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On the same drive as all your other prerequisites, create a folder labeled "PHP".
</p>
<br />

<p>
<img src="https://i.imgur.com/V7LcgzP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download the PHP Non-Thread Safe (NTS) runtime x86 (https://windows.php.net/download/), and then EXTRACT it into the "PHP" folder from the last step. Also, if necessary, install the x86 VC_Redist pack (https://www.microsoft.com/en-au/download/details.aspx?id=53587)
</p>
<br />

<p>
<img src="https://i.imgur.com/NO6M8o8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download MySQL (https://dev.mysql.com/downloads/mysql/) and run the "typical installer". When prompted, create credentials. 
</p>
<br />

<p>
<img src="https://i.imgur.com/evR1F7o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Launch IIS in Administrator mode and navigate to "PHP Manager". Where prompted select "Register and new PHP". Navigate to the "PHP" folder from before, select the "php-cgi" executable as the new PHP, and then restart the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/wTWZE75.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and unzip osTicket. Inside the unzipped osTicket folder, copy the "upload file". Navigate to "wwwroot" folder (Windows drive > inetpub > wwwroot) and paste the "upload" folder into it. Then, RENAME the "upload" folder exactly to "osTicket". Restart the server once again.
</p>
<br />

<p>
<img src="https://i.imgur.com/izkhtFU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open ISS and navigate to osTicket (Sites > Default website > osTicket), select "enable or disable an extension", and enable all three of the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll.
</p>
<br />

<p>
<img src="https://i.imgur.com/qE65YY8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate through: inetpub > wwwroot > osTicket > include > ost-sampleconfig.php. Change "ost-sampleconfig.php" to exactly "ost-config.php". Open the properties of this file and assign user permissions.
</p>
<br />

<p>
<img src="https://i.imgur.com/xgFuHBH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and run the HeidiSQL installer (https://www.heidisql.com/download.php). Link the appropriate credentials from MySQL and create a database labeled exactly "osTicket". Once finished, click the install option.
</p>
<br />

<p>
<img src="https://i.imgur.com/JVqnUxU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
And that's it! Provided all steps were followed correctly, osTicket should be installed and operational!
</p>
<br />
