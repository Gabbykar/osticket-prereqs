<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Virtual Machines
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (22H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Virtual Machines
- Remote Desktop
- osTicket installation files
- SQL
  

<h2>Installation Steps</h2>

<h3>1.) Creating a Virtual Machine</h3>

In Microsoft Azure, we will create a VM and add it to a new Resource Group, titled "osTicket". 

- **VM Name:** osticket-vm  
- **Image:** Windows 10 Pro, version 22H2 - x64 Gen2  
- **Size:** 2 vCPUs, 8 GiB memory

  

Check the licensing box and review & create the VM. No changes are needed for management, disks, or networking sections.


<p>
<img src="https://github.com/user-attachments/assets/4beec4b3-d88f-47d0-ab62-fb6914c579cb"/>
  
</p>


<p>
<img src="https://github.com/user-attachments/assets/b250bed8-699c-40c4-82aa-d6829dc1d2a9"/>

</p>

<p>
<img src="https://github.com/user-attachments/assets/71d3e404-bdb2-4c4a-be2d-716f20b4ebf4"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/a4211678-ea8a-496e-9dcd-7678c2b92c35"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/b14e9993-5c26-4baf-ae65-7f26babb349f"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/57840a92-0e8f-45a3-b8c3-d666875d4338"/>
  
</p>







<h3>2.) Accessing the Virtual Machine</h3>

- Log into the VM using **Remote Desktop** with the credentials created during the VM setup and the VM Public IP Address.

<p>
<img src="https://github.com/user-attachments/assets/bfb6429e-2e8d-41a7-8ead-4636a56769b5"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/e6e67801-b997-4823-8e68-cb8890cad620"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/115bc06b-f77a-4369-a7cf-0a1a74a95c9c"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/07fed4f7-fd0c-49e0-8c17-7ec8027243d9"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/dc7e6810-94ea-4149-974c-c3c1fb8154c5"/>

</p>



<h3>3.) Download and Prepare Installation Files</h3>

- Within the VM, download the `osTicket-Installation-Files.zip` and unzip it to your desktop. The folder should be named `osTicket-Installation-Files`.

<p>
<img src="https://github.com/user-attachments/assets/591d028b-1f25-4dbd-9ec4-10c0652780ce"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/52b54394-07e9-4d50-b2fc-1001386df152"/>

</p>



<p>
<img src="https://github.com/user-attachments/assets/41c3522f-9c8b-4541-998c-5fe38a426d49"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/0942ff1a-4822-4d95-816c-31aa0342aace"/>

</P>


<p>
<img src="https://github.com/user-attachments/assets/ad6d4c7c-ce65-47b3-a218-5356f4750978"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/848e7268-5717-41a5-ab9f-4588d13d3030"/>
  
</p>




<h3>4.) Install IIS and Enable Required Features</h3>

- Open **Control Panel** -> **Programs** -> **Turn Windows features on or off**.
- Install/enable **IIS** with the following features:
  - **World Wide Web Services** -> **Application Development Features** -> [X] CGI

<p>
<img src="https://github.com/user-attachments/assets/20adcc71-824b-4e37-9a50-8bcafc1d901c"/>
</p>


<p>
<img src="https://github.com/user-attachments/assets/6509b145-284c-4cdf-a75e-8a2720c46427"/>
</p>


<p>
<img src="https://github.com/user-attachments/assets/ffedecac-bff0-4ccf-ae8f-6df93a9feb61"/>
</p>


<p>
<img src="https://github.com/user-attachments/assets/09db49ed-03b1-409d-a5a9-815871603185"/>
</p>


<p>
<img src="https://github.com/user-attachments/assets/248854ee-0d68-4ff5-acea-3dcdc2c3b156"/>
</p>



<h3>5.) Install Required Components</h3>

- From the `osTicket-Installation-Files` folder:
  - Install **PHP Manager for IIS**: `PHPManagerForIIS_V1.5.0.msi`.
  - Install **Rewrite Module**: `rewrite_amd64_en-US.msi`.
 
<p>
<img src="https://github.com/user-attachments/assets/9e7b81a6-ccb0-4fd2-a8d4-4d696656f059"/>
</p>

<h3>6.) Setup PHP</h3>

- Create the directory `C:\PHP`.
- Unzip `PHP 7.3.8` (`php-7.3.8-nts-Win32-VC15-x86.zip`) into the `C:\PHP` folder.
- Install `VC_redist.x86.exe`.

<p>
<img src="https://github.com/user-attachments/assets/08218ce4-6304-4da4-aa56-5940fc8acaea"/>

</p>


<p>
<img src="https://github.com/user-attachments/assets/8be6d90e-ac01-48df-b554-a5e4a2a90ea5"/>

</p>



<h3>7.) Install MySQL</h3>

- From the `osTicket-Installation-Files` folder, install MySQL 5.5.62 (`mysql-5.5.62-win32.msi`).
  - Select **Typical Setup**.
  - Launch the Configuration Wizard:
    - **Standard Configuration**
    - Input a username and password, don't forget this!

<p>
<img src="https://github.com/user-attachments/assets/d03588c4-600f-4dc1-b6d0-9597343d04e5"/>

</p>

<h3>8.) Configure IIS</h3>

- Open IIS as an administrator.
- Register PHP:
  - Go to **PHP Manager** -> Register PHP path -> `C:\PHP\php-cgi.exe`.
- Reload IIS (Stop and Start the server).

<p>
<img src="https://github.com/user-attachments/assets/b89714b5-e336-4ed0-bc81-a3e6df2ff893"/>

</p>

<p>
<img src="https://github.com/user-attachments/assets/eaecd813-b200-42c7-989f-4826599a7545"/>

</p>

<h3>9.) Install osTicket</h3>

- From the `osTicket-Installation-Files` folder:
  - Unzip `osTicket-v1.15.8.zip`.
  - Copy the `upload` folder into `C:\inetpub\wwwroot`.
  - Rename the `upload` folder to `osTicket`.
- Reload IIS (Stop and Start the server).

<p>
<img src="https://github.com/user-attachments/assets/4f9204cb-aff7-4038-9bec-12d0fb7d7a63"/>

</p>

<p>
<img src="https://github.com/user-attachments/assets/f1ff496e-6972-4ae3-8661-4cc6fd662657"/>

</p>

<h3>10.) Configure osTicket</h3>

- Open IIS:
  - Navigate to **Sites** -> **Default** -> **osTicket**.
  - On the right, click **Browse *:80**.

<p>
<img src="https://github.com/user-attachments/assets/088addaf-533f-4a69-8b9a-0e841c57d5ed"/>

</p>

<p>
<img src="https://github.com/user-attachments/assets/592500a5-ad12-43e7-b226-cf50f917aca8"/>

</p>

<p>
  
<img src="https://github.com/user-attachments/assets/f43e6564-309f-4961-8c5a-4f655f618666"/>

</p>

<p>

<img src="https://github.com/user-attachments/assets/c5586e32-87fa-4a41-9602-cb5ffe666f80"/>





- Note extensions that are not enabled. Go back to IIS:
  - Navigate to **Sites** -> **Default** -> **osTicket**.
  - Double-click **PHP Manager** -> Click **Enable or disable an extension**.
  - Enable the following extensions:
    - `php_imap.dll`
    - `php_intl.dll`
    - `php_opcache.dll`

<p>
<img src="https://github.com/user-attachments/assets/4ea3f01f-e3ec-43c6-acb6-c0e4704f6718"/>

</p>
<img src="https://github.com/user-attachments/assets/7426e7f5-74ec-4dac-bd92-f70046ef512c"/>


</p>

<h3>11.) Update Configuration Files</h3>

- Rename `ost-config.php`:
  - From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
  - To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`.
- Assign Permissions:
  - Disable inheritance -> Remove all permissions.
  - Add new permissions -> **Everyone** -> **Full control**.

<p>
<img src="https://github.com/user-attachments/assets/f3560ce5-4ce5-4a8f-9b2f-5d7c5e12e6d5"/>
/>
</p>

<p>
<img src="https://github.com/user-attachments/assets/946ec582-b59d-4861-af5e-cb6f6b78b8cd"/>

</p>

<h3>12.) Complete osTicket Setup</h3>

- In the browser, continue the osTicket setup:
  - Set **Helpdesk Name**.
  - Set **Default email** (receives emails from customers).

<p>
<img src="https://github.com/user-attachments/assets/f8461587-915c-4cd7-8581-81480583250d"/>

</p>

<h3>13.) Install HeidiSQL and Configure Database</h3>

- From the `osTicket-Installation-Files` folder, install **HeidiSQL**.
- Open HeidiSQL:
  - Create a new session: **Username:** root / **Password:** root.
  - Connect to the session.
  - Create a database named `osTicket`.

<p>
<img src="https://github.com/user-attachments/assets/e8caa8f4-2f19-4c76-bf39-0eb087e45a83"/>


<p>
<img src="https://github.com/user-attachments/assets/2eb699e5-1e1f-45b7-8ceb-b34b6c9c248"/>


<p>
<img src="https://github.com/user-attachments/assets/88505ac5-1152-4b0e-b111-6af4e78f3d12"/>



<h3>14.) Finalize osTicket Installation</h3>

- In the browser, complete the setup:
  - **MySQL Database:** osTicket  
  - **MySQL Username:** root  
  - **MySQL Password:** root  
- Click **Install Now!**

<p>
<img src="https://github.com/user-attachments/assets/cde82043-950a-4357-b186-a324954def87"/>

</p>

<h3>15.) Verify Installation</h3>

- Access your help desk login page: `http://localhost/osTicket/scp/login.php`.

<p>
<img src="https://github.com/user-attachments/assets/925bb6fb-828e-4a0f-a8d3-be88f67b1350"/>

</p>

<h2>Conclusion</h2>

Congratulations! You have successfully installed and configured osTicket on your virtual machine. Your help desk system is now ready to use!
