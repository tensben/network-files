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
Next, select write-access. We were granted access to open the folder and add files.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 162644](https://github.com/user-attachments/assets/5133dd68-5826-4d31-936b-31c2e33e9c46)

</p>
<p>
Let's try to select the no-access folder. As you can see, we can’t even access the folder.
</p>
<br />


<p>
  
![Screenshot 2025-02-07 162722](https://github.com/user-attachments/assets/32c52445-62a8-4b53-83ad-139e7a3bc888)

</p>
<p>
For the next portion of this lab, we will create an “ACCOUNTANTS” Security Group, assign permissions, and test access.  Let's go back to DC-1.

In DC-1, go to Active Directory Users and Computers(ADUC), right-click mydomain.com, select New, and select Organizational Unit. Name the folder  _GROUPS. Then, select _GROUPS, right-click New, and select Group.  Name the group's ACCOUNTANTS; the second line should be the same. Leave everything else the same; hit OK.

</p>
<br />

<p>
  
![Screenshot 2025-02-07 162927](https://github.com/user-attachments/assets/47b9306b-9cee-4a3f-ab21-b5212b2ee95e)

![Screenshot 2025-02-07 163013](https://github.com/user-attachments/assets/3d48c1c2-f05c-435c-a3b9-b9ee5f7ff4d2)

![Screenshot 2025-02-07 163053](https://github.com/user-attachments/assets/b0055dca-d751-48af-82da-572b89fcf0fb)

![Screenshot 2025-02-07 163122](https://github.com/user-attachments/assets/d08900a7-4bf0-4d33-ac79-6db86488708d)

![Screenshot 2025-02-07 163151](https://github.com/user-attachments/assets/5a2b6340-abfe-4752-b17f-d1731f2076ce)

![Screenshot 2025-02-07 163225](https://github.com/user-attachments/assets/40aaf15c-1497-4f1b-9f26-1785f50baa75)

</p>
<p>
Next, we will set the permissions level in the accounting folder created earlier in the lab. Select the accounting folder in C:\ drive.  Right-click the accounting folder, Properties, Sharing,  Share, type or paste ACCOUNTANTS, Add, below Permission level, select Read/Write, Share, Done, and Done. 
</p>
<br />

<p>
  
![Screenshot 2025-02-07 163254](https://github.com/user-attachments/assets/668713ae-cd8b-4f4b-9a50-2048f83487b5)

![Screenshot 2025-02-07 163316](https://github.com/user-attachments/assets/23a60bd5-22fc-4759-9b72-40361b58b471)

![Screenshot 2025-02-07 163433](https://github.com/user-attachments/assets/f9a33ff5-9d5f-431a-a91f-ff9a324ab74c)

![Screenshot 2025-02-07 163513](https://github.com/user-attachments/assets/fc21d5a9-b772-47e4-a800-b5f3757dc85c)

![Screenshot 2025-02-07 163533](https://github.com/user-attachments/assets/9b80f8c0-49d2-4c94-a69e-2c5fdfc901a1)

</p>
<p>
Go back to client-1 and try to access the account folder. Click on the accounting folder, and a window will pop up stating that we did not have access to the folder. Log out of client-1. Then, go back to DC-1 and make the user a member of the ACCOUNTANTS Security Group to gain access to the accounting folder. 
</p>
<br />

<p>
  
![Screenshot 2025-02-07 163709](https://github.com/user-attachments/assets/e2b70222-64f8-4a27-b5b1-dcdacfd9d400)

</p>
<p>In ADUC, double-click the ACCOUNTANTS folder. Go to Members, select Add, add the user, check the names, and then OK.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 163843](https://github.com/user-attachments/assets/3007cff2-c57c-4e87-af31-203536c9c00c)

![Screenshot 2025-02-07 163902](https://github.com/user-attachments/assets/3c7b6b45-5bb9-44d9-9d96-57c3da2121b9)

![Screenshot 2025-02-07 163931](https://github.com/user-attachments/assets/b0765934-8f6d-4932-9448-cc5e1f0c2067)

![Screenshot 2025-02-07 164000](https://github.com/user-attachments/assets/788b0acb-6065-4e6f-96f8-9eafe1a52f61)

</p>
<p>
Sign back into client -1 using the user you gave access to the accounting file. Open the File Explorer, type in dc, and press enter. Select the accounting folder, and the user can access the account folder. Create a file in the folder and save it. It works.
</p>
<br />

<p>
  
![Screenshot 2025-02-07 164217](https://github.com/user-attachments/assets/f98d1ccd-81ba-43d8-a900-3dc5075ebaa7)

![Screenshot 2025-02-07 164246](https://github.com/user-attachments/assets/51a35b09-f1d8-4b57-abf9-d3c2610d13db)

![Screenshot 2025-02-07 164317](https://github.com/user-attachments/assets/3ab8a0b7-5230-491d-b454-2e1349500ccd)


</p>
<p>

Instead of just adding one user to the ACCOUNTANTS group, we can add the domain users to the accounting group. Select the ACCOUNTANTS Properties, then Members, and add domain users.  All domain users now have access to the ACCOUNTANTS group. Groups can be members of other groups.

</p>
<br />

<p>
  
![Screenshot 2025-02-07 164705](https://github.com/user-attachments/assets/e38993ac-76ad-4136-a50c-6b7484fa8f71)

![Screenshot 2025-02-07 164719](https://github.com/user-attachments/assets/b2f7a47f-502f-433a-94e3-22b8979f9f10)
  
</p>
<p>
Now select any user from the domain and log in to client-1. Go back to File Explore, type in \\dc, and enter. You should now be able to select the accounting folder.
</p>
<br />





