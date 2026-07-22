<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/><img width="350" height="350" alt="Paddys_Repairs_Logo_2026_Final" src="https://github.com/user-attachments/assets/98e19316-676d-4d1e-aece-c3e9680267f5" />
</p>

<h1>osTicket - Setup and Post-Install Configuration</h1>
This project outlines the post-install configuration of the open-source help desk ticketing system osTicket customized and branded for Paddy's Repairs including some examples of some tickets "worked" to showcase life cycle and implementation of the ticketing platform.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

- <h2>Install Overview Objectives</h2>
- Downloading the files.
- Successfully installing plugins and setting up IIS.
- Extracting files to required locations on hard drive.
- Installing and enabling osTicket on SQL Database.

<h2>Post-Install Configuration Objectives</h2>

- Successfully setup client and admin portals for both parties to access platform efficiently.
- Demo and showcase example tickets to reflect working ticketing.
- Make the system environment look like it belongs to specific brand (In this case Paddy's Repairs)
- Show working knowledge of Azure, Virtual Machines and osTicket.

<h2>Install Steps</h2>

<h2>Step 1, Download Files</h2>
<p>
<img width="1288" height="700" alt="Install_Step_1_File_Folder" src="https://github.com/user-attachments/assets/755cb0f6-e477-44ad-bb8a-d31e0b1f9f1f" />
</p>
Downloaded osTicket from its resouce page on the website: 
https://osticket.com/download/ 
Once complete extract the folder via 7zip or whatever extractor of choice to downloads folder.

<h2>Step 2, Extract PHP folder!</h2>
<p>
<img width="1870" height="1003" alt="Install_Step_4_Create" src="https://github.com/user-attachments/assets/d1f7f956-0f80-430e-8b1c-6a6fe22b888c" />
<p>
<img width="1920" height="1080" alt="Install_Step_2_PHP_Extract" src="https://github.com/user-attachments/assets/5a89fe96-06d3-4bf0-8c15-6d66a7ca0630" />
</p>
Create a folder on your c: drive named "PHP" and move/ copy the PHP folder in the osTicket install files to it as shown.

<h2>Step 3, Install Packages in Folder</h2>
<p>
<img width="1053" height="652" alt="Install_Step_3_Rewrite" src="https://github.com/user-attachments/assets/bd7a860e-faac-4683-8e59-e2de6031fe49" />
</p>
Install and go through the prompts in the for the rewrite_amd installer and wait for it to finish installing.
<p>
<img width="1165" height="782" alt="Install_Step_5_Install_VC" src="https://github.com/user-attachments/assets/d164cdda-d46d-4ba3-9c87-5471f55eb396" />
</p>
Next install VC_redist.x86 packages. Your PC probably already will have them installed but in the case of installing this on an Azure remote machine. Ran it fine and installed them.
<p>
<img width="1500" height="732" alt="Install_Step_6_SQL" src="https://github.com/user-attachments/assets/538f37e8-120f-4dc5-9ecb-91dbc6bdd592" />
<p>
<img width="1920" height="1080" alt="Install_Step_6_SQL_2" src="https://github.com/user-attachments/assets/7f0e012c-1686-4095-a25b-43bf15aab53e" />
</p>
<img width="1920" height="1080" alt="Install_Step_6_SQL_3" src="https://github.com/user-attachments/assets/a82bdb27-be59-4ef9-bb18-ec5a66da42c9" />
</p>
<img width="810" height="867" alt="Install_Step_11_Create_Database" src="https://github.com/user-attachments/assets/12a1c7ea-5020-4a58-84d6-fd9e693739cf" />
<p>
<img width="818" height="873" alt="Install_Step_11_Create_Database_2" src="https://github.com/user-attachments/assets/f25acaa1-c1c7-4c8c-b4d7-36d2f712b828" />
</p>
Install the SQL database which is required for osTicket to function properly. Typical install and created a simple password for the root login for the database.

<h2>Configuration "Login" Panels</h2>

<p>
<img width="1920" height="1080" alt="Admin_Login" src="https://github.com/user-attachments/assets/ac793099-3f05-4450-9e33-c51acc606fa0" />
</p>
<p>
To start of the showcase here is the snapshot of what the administrator window looks like for the brand. Uploaded my own logos and branding to give a more personal feel to the ticketing system.
</p>
<br />
<p>
<img width="1920" height="1080" alt="Login_Users" src="https://github.com/user-attachments/assets/21f8916b-8df9-4145-98bc-40ab5af5912c" />
</p>
<p>
The login for the "users" of the platform is a lot more generic. Implemented so that users did not need to be registered with an email and password to be able to submit tickets. In theory if this was implemented officially it would allow general public to submit tickets for general personal device issues.
</p>
<h2>How to Change "branding" in osTicket</h2>
</p>
Fairly straight forward! All you have to do is go to "Admin Panel" in the top right. Once there, Click "Settings" then go to "Company". Under the "Company" tab you will see the tabs "Logos" and Backdrop". You can navigate to those tabs respectively to change your branding to change up from the generic osTicketing setup.
<p/>
  <img width="1920" height="1080" alt="Change_Logo" src="https://github.com/user-attachments/assets/fbc7bd4c-9dcf-49c7-9c59-0e28f66dafbd" />
</p>
<img width="1920" height="1080" alt="Change_Backdrop" src="https://github.com/user-attachments/assets/06af1e09-6b31-4dea-8a69-bdc2384ead77" />
<br />
<h2>Agent Setup</h2>
<p>
<img width="1920" height="1080" alt="Agent_Setup" src="https://github.com/user-attachments/assets/fe687e3c-d230-49ba-ba68-bbed0af470ca" />
</p>
<p>
For this scenario I only setup my self as the agent servicing this help desk. Mocked up to be a one person "Help Desk" and "Repair Technician"
</p>
<h2>Users Listed</h2>
</p>
<img width="1920" height="1080" alt="Users_Setup" src="https://github.com/user-attachments/assets/eb7c058e-c962-4984-93c1-594d140a0d27" />
</p>
I only registered a few users while setting up this excerise/ project. Since I am fairly big Pokemon Fan. I decided to setup fictional scenarios assisting characters in that universe with their tech needs as a help desk agent.
<br />
<h2>Help Topics Added</h2>
</p>
I wanted to have a healthy variety of issues to choose from if a client were to reach out for assistance using the platform. The topics I included in the ticketing system are listed below:
</p>
<img width="1920" height="1080" alt="Help_Topics_Paddy&#39;s_Repairs" src="https://github.com/user-attachments/assets/ce160d3e-e2ad-4c02-87c4-556649dca080" />
</p>
<br />
<h2>Working Ticket Cycle Example 1 "Prof Oaks Business Critical Network Issue"</h2>
</p>
The first ticket example I "worked" was pretending that Prof Oak of the Kanto region had a "Business Critical" network outage at the lab... with a very silly and straight foward fix to the issue!
</p>
<img width="1920" height="1080" alt="Shot_1" src="https://github.com/user-attachments/assets/d060ae33-698e-49a7-a460-58231895113b" />
</p>
<img width="1920" height="1080" alt="Shot_2" src="https://github.com/user-attachments/assets/96113f9a-e268-4d46-868d-0374ccb713ae" />
</p>
<img width="1920" height="1080" alt="Shot_3" src="https://github.com/user-attachments/assets/8396fbd6-9b71-434f-9830-8c20426382ff" />
<br />
<h2>Working Ticket Cycle Example 2 "Hilda's Password Reset"</h2>
</p>
A very simple password reset ticket! Hilda needed to reset password because she couldn't access the storage system to change up her team for the big gym challenge the next day!
</p>
<img width="1920" height="1080" alt="Shot_1_Hilda" src="https://github.com/user-attachments/assets/214c5624-0ec9-4f8d-a4a1-1c32c7b04d4a" />
</p>
<img width="1920" height="1080" alt="Shot_2_Hilda" src="https://github.com/user-attachments/assets/50ef8457-b95f-4db8-b153-160d1368e849" />
</p>
<img width="1920" height="1080" alt="Shot_3_Hilda" src="https://github.com/user-attachments/assets/f4dbad62-e7c1-4a4d-9ee2-124a46143c94" />
</p>
<h2>Tickets Successfully Worked and Closed!</h2>
</p>
<img width="1920" height="1080" alt="Closed_Tickets" src="https://github.com/user-attachments/assets/e55538ca-12ce-4b43-945b-f85b0e8ae7cd" />
</p>
<h2>Thank you for overviewing my implementation of osTicket!</h2>
