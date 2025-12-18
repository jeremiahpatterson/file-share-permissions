<p align="center">
<img src="https://i.imgur.com/LUGkZMe.jpeg" alt="Traffic Examination"/>
</p>

<h1>File Sharing and Permissions Configuration</h1>
In this tutorial, we will configure file sharing and allow Read, Write, or Deny access to individual users or groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory

<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter - x64 Gen2
- Windows 10 Enterprise, version 22H2 - x64 Gen2

<h2>High-Level Steps</h2>

- Step 1 - On the Domain Controller C-drive, create 4 folders: “read-access”, “write-access”, “no-access”
- Step 2 - Set the following permissions (share the folder)
           Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
           Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
           Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
- Step 3 - From the Client as a non-admin user, test which folders you can access and modify.
- Step 4 - Create a Security Group named ACCOUNTANTS and add a User.
- Step 5 - Verify User access.
- Task Complete

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/BoptCeJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On the Domain Controller C-drive, create 4 folders: “read-access”, “write-access”, “no-access”, and accounting.
</p>
<br />

<p>
<img src="https://i.imgur.com/8I9HSbe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click on each folder, click Properties, select the Share tab, and click the Share button. Enter the group or user/s that it will be shared with, then click Add. Select the Premission Level and press Share. 
</p>
<br />

<p>
<img src="https://i.imgur.com/MyuXNQA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Client VM, navigate to the search bar and enter: \\ name of Domain Controller. In this example, it is "\\dc-1". You can also click Start, Run, "\\dc-1". (No quotes around) dc-1.
Click on the files to see which ones you do and do not have access to.
</p>
<br />

<p>
<img src="https://i.imgur.com/iP0JdZP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, let's create a Security Group. In these examples, in ADUC, we created an Organizational Unit named _GROUP to place the Security Group, but this is optional. Click on one of the folders and select New, then Groups. Enter the desired name of the Group and press OK.
</p>
<br />

<p>
<img src="https://i.imgur.com/Saf6Bv9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We can now add a User. In the above example, you can see that the user is not able to access the accounting folder. To add a user to the Security Group, right-click on the group and select Properties. Select Members, then Add. Enter the User and click Check Names, followed by OK. Now that the User has access, as seen below.
</p>
<p>
<img src="https://i.imgur.com/ozcNHhZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
