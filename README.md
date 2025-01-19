<h1>Creating a Network File Share and accessing it with a User Account</h1>
This demonstration shows how to create a network file share and then using a user account within the same domain to access the file. This environment consists of a Windows Server 2022 virtual machine acting as the Domain Controller on a VNet with a Windows 10 virtual machine acting as a client within the same VNet. These virtual machines and this VNet was created with Microsoft Azure. The Domain Controller has Active Directory installed on it. The Domain Controller and the client on the VNet are both connected to the same domain. I am connecting to the Domain Controller and the client via Remote Desktop Protocol through my local device which is a Windows 11 computer.<br />

<h2>Environments and Technologies used</h2>

- Microsoft Azure
- Remote Desktop Protocol
- Active Directory

<h2>Operating Systems used</h2>

- Windows 11 (Local Device)
- Windows 10 (Virtual Machine - Client)
- Windows Server 2022 (Virtual Machine - Domain Controller)

<br />

<h2>Creating a Network File Share</h2>

<p>
  <img src="https://github.com/user-attachments/assets/dff0773f-388e-4770-841c-2148ed3ea37b" height="80%" width="80%">
</p>
<p>The first thing you want to do when creating a network file share is to log into the Domain Controller with your administrator account. Now click "Start" and then click "File Explorer" to open the File Explorer page. Once you're in this screen, click "This PC" and then double-click "Windows (C:)" under "Devices and drives" to open the C-drive.</p> <br/>

<p>
  <img src="https://github.com/user-attachments/assets/ef957765-c443-44d2-8296-e27f065a9910" height="80%" width="80%">
</p>
<p>Once you're in the Windows C-drive, right-click on some blank space within the section, hover your cursor over "New", and click "Folder" to create a new folder. You can name the folder whatever you want. In this case I am going to name it "Read Only". </p><br />

<p>
  <img src="https://github.com/user-attachments/assets/1ef766aa-2b5e-4e9a-a1be-74d281d51e07" height="50%" width="40%">
</p>
<p>From here, right-click on the new folder you created, click on "Properties", and then click on the "Sharing" tab. This is the tab we will enter to share the folder we created.</p><br />

<p>
  <img src="https://github.com/user-attachments/assets/09f6d04b-cd4c-47c6-86c6-1fc4ef57b1e7" height="50%" width="50%">
</p>
<p>Now click on "Share..." and type in "domain users" so that way we can share the folder with all of the users on the domain. Once you type in "domain users", click "Add". At this point you can view the "Permission Level" next to "Domain Users" you added to see if that is the permission level you want set to the domain users who have access to the file share, or you can change it to the most appropriate level if needed. Now click "Share".</p><br />

<p>
  <img src="https://github.com/user-attachments/assets/225ce557-bdb0-4725-b475-6ff30bfa79c1" height="50%" width="50%">
</p>
<p>You should get a confirmation saying "Your folder is shared.". From here you can click on "Done". You can aslo click "Close" on the properties window of the folder you created and exit out of File Explorer. The folder has been shared successfully and now we are going to verify that one of our normal user accounts has access to the network file share.</p><br />

<h2>Verifying that a normal user account has access to the network file share</h2>

<p>
  <img src="https://github.com/user-attachments/assets/842099a2-1b6d-4e5a-8856-4d278cc099f5" height="80%" width="80%">
</p>
<p>Now we can log into our client device with a normal user account (I am using Remote Desktop Protocol to log into a client device which is a Windows 10 virtual machine). Once logged in, open File Explorer. Click in the search bar where it says "Quick access" and type in the network path to the Domain Cotroller. For this project, my Domain Controller is called "dc-1" so I will be putting "\\dc-1" in the search bar, now press enter.</p><br />

<p>
  <img src="https://github.com/user-attachments/assets/5c09a514-b182-4f64-8727-5149efaba559" height="80%" width="80%">
</p>
<p>You should now see the folder you shared when you where logged into your Domain Controller as an administrator (mine is called "Read Only"). Double-click the folder to verify you have access to it.</p><br />

<p>
  <img src="https://github.com/user-attachments/assets/ff76e7b9-7bb8-43df-afda-e4a966d8f111" height="80%" width="80%">
</p>
<p>In this case, the folder is empty because we didn't put anything inside of the folder but you can see that you still have access to the folder and the folder was shared over the network successfully.</p>
