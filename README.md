
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>


<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- Rewrite Module
- MySQL 5.5.62
- Heidi SQL

![image](https://github.com/user-attachments/assets/4616b7df-e146-481f-bf03-2dc41d8962af)


<h2>Installation Steps</h2>
1- CREATE VIRTUAL MACHINE ON AZURE
 The first step is to create a (VM)Virtual Machine on Azure. Choose the image Windows 10 Pro, version 22H2
 
![image](https://github.com/user-attachments/assets/eaf2700a-aff3-4cd4-87fe-4d83464a0bc9)
*** Make sure to set the size to 2 or 4 vcpus and 8/16 Gib memory. Make sure RDP(3389) is allowed in "Select inbound
ports" to allow Remote Desktop access the VM.
![image](https://github.com/user-attachments/assets/ee8e4a94-2160-484f-b1d8-a8ecc3585ab9)

2-REVIEW & CREATE 
Click on the last check box to confirm an elgible Windows 10 License ,then proceed to "Review and Create". A validation process will occur before being able to create.

3-FIND YOUR (VM) PUBLIC IP ADDRESS 
Allow time for your deployment to complete, then locate ypur VM public IP address and copy it.

![image](https://github.com/user-attachments/assets/eb356d8a-22b7-4568-a713-e3a7623059d9)


4- CONNECT TO YOUR VM USING REMOTE DESKTOP 
Open your Remote Desktop Connection and paste your VM IP address, then with the password & username you created
within the VM.



![image](https://github.com/user-attachments/assets/c857e29e-f2e3-486f-a328-78b7f724ec69)

5- ENABLE IIS
Once the VM is open, we will need to install/enable IIS. Open control panel->Programs-> Turn Windows features on or off

![image](https://github.com/user-attachments/assets/016992da-ed56-441b-94b0-ed1f08342edb)

ENABLE AND EXPAND THE HIGHLIGHTED FEATURES :

![image](https://github.com/user-attachments/assets/e233ba68-8cbb-4d4a-aa2f-8f8a10a718dc)

=INTERNET INFORMATION SERVICES
=WEB MANAGEMENT TOOLS
=IIS MANAGEMENT CONSOLE 
=WORLD WIDE WEB SERVICES
=APPLICATION DEVELOPMENT FEATURES
=CGI
=COMMON HTTP FEATURES 

CLICK OK THE FEATURES SHOULD BE ENABLED.

6- DOWNLOAD AND INSTALL PHP MANAGER (INSTALLATIONS FILES)


![image](https://github.com/user-attachments/assets/88a23fb1-adc1-4439-806f-10d6303841a9)

7- DOWNLOAD & INSTALL REWRITE MODULE (INSTALLATION FILES)

![image](https://github.com/user-attachments/assets/7a9fd932-c015-4fce-b6c8-685fe2871271)

8- CREATE NEW DIRECTORY 
PROCEED TO FILE EXPLORER & CREATE THE DIRECTORY IN WINDOWS "C". RENAME FOLDER PHP 

![image](https://github.com/user-attachments/assets/1e3f8534-e3f9-47eb-ae43-0e38f7f86afa)

9- DOWNLOAD & INSTALL PHP 7.3.8 FROM THE (INSTALLATION FILES) AND EXTRACT IN TH NEW PHP FOLDER 

![image](https://github.com/user-attachments/assets/f896f08f-7b5d-4fc1-a033-017369a446b4)

10- DOWNLOAD & INSTALL VC_redist.x86.exe

11- DOWNLOAD & INSTALL MySQL 5.5.62 (INSTALLATION FILES) 
TYPICAL SETUP->LAUNCH CONFIGURATION WIZARD AFTER INSTALL-> STANDARD CONFIGURATION

![image](https://github.com/user-attachments/assets/4f70df80-a2bf-4c6b-a701-ec47fb1a541e)

12-LAUNCH IIS AS AN ADMIN (SEARCH IIS IN THE WINDOWS SEARCH BAR, THEN RIGHT CLICK SELECT OPEN AS ADMINISTRATOR)

13-REGISTER PHP MANAGER

![image](https://github.com/user-attachments/assets/4e79828c-c3a8-4b1f-98f8-ab329216534b)

NOTE: YOU WILL BE REQUIRED TO PROVIDE A PATH TO "php-cgie.exe". LEAD IT TO THE PHP FOLDER YOU CREATED YOU WILL FIND THE FILE "PHP-CGI".

14-RESTART THE IIS SERVER (BUTTON ON RIGHT SIDE OF THE WINDOW UNDER ACTIONS->MANAGER SERVER).

![image](https://github.com/user-attachments/assets/2005211a-d1de-4cca-9b5a-412cb479a6c3)

15- DOWNLOAD & INSTALL osTICKET (INSTALLATION FILES) EXTRACT THE CONTENTS  INTO c:\inetpub\wwwroot

![image](https://github.com/user-attachments/assets/2b3c56cc-4722-4b82-a537-9013aaafbbc3)

NOTES= WITHIN THE C:\INETPUB\WWWROOT, RENAME "UPLOAD" TO "osTICKET"

16- RESTART IIS AGAIN ( TOP RIGHT OF SCREEN)

![image](https://github.com/user-attachments/assets/23222527-f8ab-4760-be36-6b6a83134e52)

17- LAUNCH osTICKET 
UNDER  CONNECTIONS INSIDE OF (IIS) VM-osTICKET-> SITES->DEFAULT WEB SITE->osTICKET

![image](https://github.com/user-attachments/assets/9a0ad587-9415-4bcb-b293-24b5e627bd99)

** CLICK ON osTICKET **

18- SELECT BROWSE *80 TO LAUNCH osTICKET (RIGHT SIDE OF WINDOW) 

![image](https://github.com/user-attachments/assets/57cb5d2e-82d6-4350-b7a0-524b88185e9a)

***THIS SHOULD OPEN UP osTICKET IN A SEPARATE WINDOWS BROWSER***

![image](https://github.com/user-attachments/assets/822e0712-8026-472c-9c2c-aa3bfc73ece4)

19- ENABLE EXTENSIONS 
   OPEN IIS ->PHP MANAGER -> SELECT ENABLE FOR THE FOLLOWING EXTENSIONS
     =php_imap.dll
     =php_intl.dll
     =php_opcache.dll
     
![image](https://github.com/user-attachments/assets/c4c48ab7-7da8-4e29-beee-d7f46e7ea036)

20- REFRESH osTICKET 
AFTER REFRESHING YOU WILL NOTICE HOW MUCH MORE FEATURES ARE AVAILABLE TO USE.

21- RENAME OST-CONFIG.PHP

GO IN C:\INETPUB\WWWROOT\OSTICKET\INCLUDE\OST-SAMPLECONFIG.PHP
RENAME IT TO "OST-CONFIG.PHP"

![image](https://github.com/user-attachments/assets/74f0f4d6-2be1-485a-9c23-e6da5caa2b34)

22- CHANGE OST-CONFIG.PHP PERMISSIONS 
*RIGHT CLICK* GO TO PROPERTIES -> ->SECURITY-> ADVANCE -> DISABLE INHERITANCE (REMOVE ALL INHERITED PERMISSIONS) ADD EVRYONE AS A PRINCIPAL. SELECT ALL BOXES TO ENSURE ALL PERNISSIONS ARE GRANTED*

![image](https://github.com/user-attachments/assets/75b4d54b-752e-4c11-8f1e-3b7c85e6a135)  

23- CONTINUE osTICKET INSTALLATION 

![image](https://github.com/user-attachments/assets/734bdbf3-9b41-4892-bf21-2bf7b3589241)

24- DOWNLOAD & INSTALL HEIDI SQL FROM THE (INSTALLATION FILES)
OPEN HEIDI SQL AND CREATE A NEW SESSION, MAKE SURE TO FILL IN THE USERNAME AS ROOT AND CREATE A PASSWORD. AFTER FILLING OUT YOUR CREDENTIALS NOW CLICK OPEN A NEW SESSION SHOULD OPEN UP.

25-  CREATE NEW DATABASE INSISE OF "HEIDI SQL"

26- FINISH osTICKET SIGN-UP 
REVERT BACK TO YOUR osTICKET BROWSER AND FILL OUT YOUR INCOMPLETE CREDENTIALS.

27- CLICK INSTALL AND osTICKET SHOULD BEGIN TO SETUP FOR YOU.

****CONGRATS YOU JUST INSTALLED osTICKET****











     
   


     








































<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
