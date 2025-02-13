<p align="center">

</p>

<h1>Network File Shares and Permissions </h1>
  
This tutorial outlines sharing resources over the network using Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

<p>
In this lab, we will share resources over the network and create file shares to allow, deny, or read access to individual users or groups. We will use DC-1 and Client-1 virtual machines (VMs).  

DC-1 login as domain admin account(mydomain.com\jane_admin).  Select from the previously created users from the Active Directory Users and Computers. Select a user in the _EMPLOYEES folder, or use the users from earlier labs. 

</p>
<br />

<p>

![Screenshot 2025-02-07 155939](https://github.com/user-attachments/assets/6765b4d9-2130-4db4-b82f-9e5bd12d84f2)

</p>


<p>
Login to client - 1 with your selected user(mydomain.com\username).
</p>
<br />

<p>

![Screenshot 2025-02-07 160326](https://github.com/user-attachments/assets/e85e0aa5-1d43-4157-a584-5923c1f6e6e6)

</p>
<p>
IN DC-1, create four folders on the C:\ called read-access, write-access, no-access, and accounting.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 160847](https://github.com/user-attachments/assets/769e9898-d956-40bf-b191-9c9f799e57ee)

</p>
<p>
Next, set the following permissions for the folders. The account folder will be used later in the lab.
</p>
<br />

<p>
  
![Screenshot 2025-02-13 122934](https://github.com/user-attachments/assets/71b70916-4a0b-4981-9841-155cbcb85b72)

</p>
<p>
Right-click the read-access folder and select Properties, then Sharing and Share. Type in domain users and Add. Under Permission level, select read, then Share.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 161055](https://github.com/user-attachments/assets/e623f115-ab2a-44f3-b376-582a8f34774f)

![Screenshot 2025-02-07 161114](https://github.com/user-attachments/assets/1ac30f40-af26-4757-9fb3-4277803aed24)

![Screenshot 2025-02-07 161135](https://github.com/user-attachments/assets/4fe8221e-2ad9-4524-8ccc-10b6dd523c27)

![Screenshot 2025-02-07 161313](https://github.com/user-attachments/assets/251cad09-bb27-44dd-9adc-a6483635bd71)

![Screenshot 2025-02-07 161354](https://github.com/user-attachments/assets/09978501-fc67-4ea2-a1bc-b21def94cac7)

![Screenshot 2025-02-07 161429](https://github.com/user-attachments/assets/2ed47353-28b4-41a8-a5e5-c155b514af77)

</p>
<p>
Repeat the same process for write-access and no-access. Ensure the write-access is in the group Domain Users and permission read/write. The no-access is domain admins group and read/write permission. 
</p>
<br />

<p>
  
![Screenshot 2025-02-07 161504](https://github.com/user-attachments/assets/2166752e-8bff-4081-a8da-8722c723b946)

![Screenshot 2025-02-07 161524](https://github.com/user-attachments/assets/a3a538b0-f4de-4828-a33e-e5a7b55493c7)

![Screenshot 2025-02-07 161547](https://github.com/user-attachments/assets/2368b1b9-32be-493a-986e-0266108ca642)

![Screenshot 2025-02-07 161653](https://github.com/user-attachments/assets/e380dc96-704a-4821-9a70-55903e06214c)

![Screenshot 2025-02-07 161732](https://github.com/user-attachments/assets/ac12c74d-c5d4-46c1-8517-1d8a940b46fc)

![Screenshot 2025-02-07 161814](https://github.com/user-attachments/assets/16578efd-22b7-492f-bed8-dfedfe0cce01)

![Screenshot 2025-02-07 161857](https://github.com/user-attachments/assets/ebc92727-0cba-4a01-9991-631483989ccc)

![Screenshot 2025-02-07 161918](https://github.com/user-attachments/assets/2104aa79-c93a-43af-982b-38311189b55d)

![Screenshot 2025-02-07 161956](https://github.com/user-attachments/assets/3933201b-9cb7-4450-96df-f616ef5231dd)

![Screenshot 2025-02-07 162045](https://github.com/user-attachments/assets/23053340-791a-4f1b-b8ff-49c2ac65cacf)

![Screenshot 2025-02-07 162101](https://github.com/user-attachments/assets/1b476ab9-8738-420a-98e4-190212bac4d7)

</p>
<p>
We will try to access the folders created in client 1. On Client 1, go to the Folder File, type in \\dc-1, and press Enter.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 162320](https://github.com/user-attachments/assets/61335d9d-5001-49d7-b91b-5078d0aa0889)

</p>
<p>
When we select the read-access folder, we can open it, but when we try to add a file, a window appears stating that we need permission. 
</p>
<br />

<p>
  
![Screenshot 2025-02-07 162459](https://github.com/user-attachments/assets/c479bddd-02d3-4f39-a6cb-39df28ad1fa4)

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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
