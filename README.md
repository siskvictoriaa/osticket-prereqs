<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=fWX1Lj-rOa0)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

Web server installed (Apache/IIS/LiteSpeed)
  PHP8.2+ installed
  
  MySQL/MariaDB installed and running
  
  Empty database created
  
  Database user with full privileges
  
  osTicket installation package downloaded and extracted
  
 Access to a web browser to run the installer turn1search1

<h2>Installation Steps</h2>

<p>
<img width="2622" height="1319" alt="image" src="https://github.com/user-attachments/assets/c154a19a-2d4d-4c74-8c29-366958493624" />
<img width="1006" height="608" alt="image" src="https://github.com/user-attachments/assets/77f80a71-e442-4f5f-bd69-c9832f40d91a" />
</p>
<p>
To begin the osTicket deployment, create a virtual machine in Azure named osticket-vm. Use Windows 11 as the operating system and configure the administrator account with the username labuser and password osTicketPassword1!. Ensure that RDP (port 3389) is enabled for remote access, along with HTTP (port 80) and HTTPS (port 443) to support web access to the osTicket application. Once the VM is deployed, connect to it using Remote Desktop and proceed with installing IIS, PHP, MySQL, and the osTicket software.
</p>
<br />

<p>
<img width="985" height="430" alt="image" src="https://github.com/user-attachments/assets/1f0eaf09-1679-4d6f-abaf-2322a0f49ab2" />
<img width="1421" height="846" alt="image" src="https://github.com/user-attachments/assets/1fec6b73-10e9-4d7b-86b5-4e27f48f0483" />
</p>
<p>
To begin the osTicket deployment, create a virtual machine in Azure named osticket-vm. Use Windows 11 as the operating system and configure the administrator account with the username labuser and password osTicketPassword1!. Ensure that RDP (port 3389) is enabled for remote access, along with HTTP (port 80) and HTTPS (port 443) to support web access to the osTicket application. Once the VM is deployed, connect to it using Remote Desktop and proceed with installing IIS, PHP, MySQL, and the osTicket software.
</p>
<br />

<p>
<img width="376" height="187" alt="image" src="https://github.com/user-attachments/assets/240f3240-22c8-4b53-a16a-79395e72746f" />
<img width="1374" height="775" alt="image" src="https://github.com/user-attachments/assets/10f1c187-d860-4eba-b597-64e91ac98f0d" />
<img width="1192" height="704" alt="image" src="https://github.com/user-attachments/assets/42cbb2c0-0b5e-4a89-a7de-61368862e6b1" />
<img width="1197" height="728" alt="image" src="https://github.com/user-attachments/assets/4586cc7e-d521-4904-898e-b083daba1f29" />
<img width="863" height="738" alt="image" src="https://github.com/user-attachments/assets/70a1b0f5-b98f-459b-9e1f-1c0f3ad3d6fb" />
<img width="1838" height="305" alt="image" src="https://github.com/user-attachments/assets/69f39194-0b9c-44a3-a444-8765af6a7464" />
<img width="640" height="187" alt="image" src="https://github.com/user-attachments/assets/efc7598c-3a90-422b-be39-a7f28ba28888" />
<img width="1282" height="788" alt="image" src="https://github.com/user-attachments/assets/eff16650-29d7-49c1-9eea-7f467ca96b1b" />
<img width="198" height="95" alt="image" src="https://github.com/user-attachments/assets/22c805dc-c0b1-4414-95f1-7ec4e64f175a" />
<img width="1914" height="696" alt="image" src="https://github.com/user-attachments/assets/20387000-ffb2-4db4-9bba-c29362c6dd4e" />
<img width="2555" height="268" alt="image" src="https://github.com/user-attachments/assets/614b491e-3a61-47c8-90e4-f649511a0dde" />

</p>
<p>
After connecting to the virtual machine, download the latest version of osTicket from the official osTicket website and save the installation package to the VM. Once the download is complete, locate the ZIP file, right-click it, and select Extract All to unzip the contents to a convenient location, such as the Desktop or Downloads folder. After the extraction process is finished, open the extracted folder and verify that all osTicket files are present. These files can then be copied to the IIS web server directory, preparing the application for configuration and installation. Unzipping the package ensures that all required files and folders are accessible and ready for deployment.
  
  After connecting to the Windows 11 virtual machine, begin by enabling Internet Information Services (IIS) through the Windows Features menu. During installation, expand World Wide Web Services, Application Development Features, and enable CGI support, which is required for PHP integration. Once IIS is installed, download and install PHP Manager for IIS and the IIS URL Rewrite Module. These tools simplify PHP configuration and provide URL rewriting capabilities required by osTicket.

Next, create a directory named C:\PHP and download PHP 7.3.8. Extract the PHP ZIP archive into the newly created folder. Afterward, install the Microsoft Visual C++ Redistributable x86 package, which provides required runtime components for PHP. Then install MySQL 5.5.62, configuring the database with the username root and password root. Once these components are installed, open IIS Manager as Administrator and use PHP Manager to register the PHP executable from the C:\PHP directory. After PHP has been registered successfully, restart IIS to apply the changes.

With the web server environment configured, copy the extracted osTicket files into the IIS web directory and proceed with the osTicket installation. Open IIS Manager and verify that the osTicket site is configured correctly. To ensure all settings are loaded properly, stop and start the IIS server or perform an IIS reset after the installation is complete. Reloading IIS allows the web server to recognize the newly installed application and confirms that PHP, MySQL, and osTicket are communicating correctly before continuing with the final configuration steps.

 In IIS Manager, expand the server name in the left navigation pane and then expand Sites. Under Sites, select Default Web Site, and then click the osTicket folder or application that was created during the installation. Once the osTicket application is selected, look to the Actions pane on the right side of the IIS Manager window. Click *Browse :80 (http) to launch the website in your default web browser. This action opens the osTicket installation page using port 80, allowing you to verify that the web application is running correctly and continue with the setup and configuration process.
</p>
<br />
