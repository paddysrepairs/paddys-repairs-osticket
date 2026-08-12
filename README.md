<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/><img width="350" height="350" alt="Paddys_Repairs_Logo_2026_Final" src="https://github.com/user-attachments/assets/98e19316-676d-4d1e-aece-c3e9680267f5" />
</p>

<h1>osTicket - Setup and Post-Install Configuration</h1>
This project outlines the initial setup briefly and post-install configuration of the open-source help desk ticketing system osTicket. Customised and branded for Paddy's Repairs including some examples of some tickets "worked" to showcase life cycle and implementation of the ticketing platform.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket
- 7zip

<h2>Operating Systems Used </h2>

- Windows 11 (Main Machine)
- Windows 10 Enterprise</b> (21H2) (Virtual Machine)

- <h2>Install Overview Objectives</h2>
- Setting up the Resource Group and Virtual Machine within Azure.
- Downloading the files.
- Successfully installing plugins and setting up IIS.
- Extracting files to required locations on hard drive.
- Installing and enabling osTicket on SQL Database.

<h2>Post-Install Configuration Objectives</h2>

- Successfully setup client and admin portals for both parties to access platform efficiently.
- Demo and showcase example tickets to reflect working ticketing.
- Make the system environment look like it belongs to specific brand (In this case Paddy's Repairs)
- Show working knowledge of Azure, Virtual Machines and osTicket.

<h2>Setting up the Virtual Machine in Azure</h2>
<p>
<img width="960" height="510" alt="Step_1_Setup_osTicket_Resource_Naming_Group" src="https://github.com/user-attachments/assets/d1af3f19-49ed-4fa0-9055-de9fab6cdb8e" />
<p>
<img width="960" height="510" alt="Step_1_Setup_osTicket_Tags_Organize" src="https://github.com/user-attachments/assets/b01698df-fc71-446e-ac92-b55917ef66c5" />
</p>
<p>
<img width="960" height="510" alt="Step_1_Setup_osTicket_Resource_Create" src="https://github.com/user-attachments/assets/aabf22fd-fa41-4926-b3f9-3311e9cb1fcd" />
<p>
Login into Azure, find the tab "create a new resource group" on your side panel of options. Calling it osTicket since that is the what we are setting up in this exercise. You can also add organizational tags as an option to help keep things more organized as you go through the setup of the virtual machine and resources for your osTicket.
</b>

<h2>Create the Virtual Network</h2>
<p>
<img width="960" height="510" alt="Step_2_Setup_osTicket_Network_Create" src="https://github.com/user-attachments/assets/c74c9b34-d3b8-4c94-aa02-0dd8f05b5d90" />
</p>
To keep in good habits we are going to setup up a new virtual network instead of allowing a default one to be created with the virtual machine. 
<p>
<img width="960" height="510" alt="Step_2_Setup_osTicket_Network_Create_Basics" src="https://github.com/user-attachments/assets/d8cc8570-da07-40b5-a2de-327a59f13f69" />
</p>
Go through and setup the basics tab. I named the network "osTicketnet". Be sure to make sure that the location of your virtual network is set in the same location that your virtual machine is going to be located in.
<p>
<img width="961" height="510" alt="Step_2_Setup_osTicket_Network_Create_Review" src="https://github.com/user-attachments/assets/39c6fa15-991a-4f24-80d2-f9dce6a883cb" />
</p>
Once you have reviewed your settings and are content with how things look. Go ahead and hit "review and create".

<h2>Setting Up the Virtual Machine in Azure</h2>
<p>
<img width="960" height="510" alt="Step_3_Setup_osTicket_VM_Create" src="https://github.com/user-attachments/assets/ac6e44db-2b49-4681-98b7-4c56aa316393" />
</p>
<p>
<img width="960" height="510" alt="Step_3_Setup_osTicket_VM_Setup" src="https://github.com/user-attachments/assets/7443f980-811c-4eca-a3af-d39f24111f41" />
</p>
Find the "create" in the virtual machine resource tab.
<p>
<img width="960" height="510" alt="Step_3_osTicket_VM_Basic_Setup" src="https://github.com/user-attachments/assets/a2bc4b3a-10bf-4d6f-a89d-15915364a3d7" />
</p>
Navigate to basics tab for setup. Settings can look something like what is shown above.
<p>
<img width="960" height="510" alt="Step_3_Setup_osTicket_VM_Setup_Network" src="https://github.com/user-attachments/assets/0cdb419d-bafb-4ed5-8fd6-e9c4620f5213" />
</p>
Like I said when setting up the virtual network, be sure to keep the virtual machines location in the same place as the network we created. At this point we can click "review+create" as these settings will suffice for this exercise on the virtual machine to run osTicket.
<p>
<img width="961" height="510" alt="Step_3_Setup_osTicket_VM_Waiting_Complete" src="https://github.com/user-attachments/assets/49db00f5-78ae-4aa9-b46b-aaa17de1fac4" />
</p>
We are done with the creation of the VM at this point! Good stuff.
<p>
<img width="960" height="510" alt="Step_4_Connect_VM" src="https://github.com/user-attachments/assets/0892b7a8-25cf-4b31-8980-d12a6d486bdd" />
</p>
Now that the virtual machine is created. Click on the machine name itself to go into its settings.
<p>
<img width="960" height="510" alt="Step_4_Connect_VM_Public_IP" src="https://github.com/user-attachments/assets/909b4297-ce73-4a34-b5fa-538411d848ca" />
</p>
Scroll down to find the virtual machines public IP address. This is what we need to connect to it with remote desktop.
<p>
<img width="305" height="193" alt="Step_4_Open_RDP_Connect" src="https://github.com/user-attachments/assets/e2ca4122-5dcf-41df-b809-7f1a09bbdf24" />
</p>
Right on! Now we can connect to the VM we are going to setup osTicket within. Time to login to your VM to begin the next steps.
</b>

<h2>Install Steps</h2>

<h2>Step 1, Download Files</h2>
<p>
<img width="774" height="488" alt="Step_1_VM_Open_Browser" src="https://github.com/user-attachments/assets/13ccfebe-9dd0-400d-902e-19b9bad4d637" />
</p>
Open your web browser in your newly created VM. In this case just going to use Microsoft Edge as default.
<p>
<img width="960" height="510" alt="Step_2_Download_osTicket" src="https://github.com/user-attachments/assets/91bdd0ee-c824-435c-ab9c-90345ff47694" />
</p>
Downloaded osTicket from its resouce page on the website: 
https://osticket.com/download/ or the link shown above.
Once complete extract the folder via 7zip or whatever extractor of choice to downloads folder.

<h2>Step 2, Download 7zip!</h2>
<p>
<img width="960" height="510" alt="Step_3_Download_7zip" src="https://github.com/user-attachments/assets/23f1e0fc-9633-4d68-a7ca-558b96a8e26b" />
<p>
Navigate to 7zips website to download it. You don't necessarily need to do this step, but I believe 7zip is a far superior extraction tool on Windows than other options.
<p>
<img width="590" height="445" alt="Step_3_Download_7zip_2" src="https://github.com/user-attachments/assets/12256c01-db71-4557-8adc-1493917d657c" />
<p>
Download the installer as shown and right click. "Run as Admin" to begin install.
<p>
<img width="960" height="510" alt="Step_4_Install_7zip_Success" src="https://github.com/user-attachments/assets/940bdfa6-6b24-4d87-aeb7-e0b8e0ab24bc" />
</p>
7zip should be sucessfully installed at this stage! Onto installing osTicket now.
<p>
<img width="590" height="445" alt="Step_5_Extract_osTicket" src="https://github.com/user-attachments/assets/f6a09083-3f06-4948-bd1b-5b96e008c0b7" />
</p>
Extract the files using 7zip which we just installed to the downloads folder. Right click "Extract here"

<h2>Turn on IIS for PHP server</h2>
<p>
<img width="590" height="445" alt="Step_7_Control_Panel" src="https://github.com/user-attachments/assets/76c27472-76e1-405f-ac0d-5f0ac9b42bf5" />
</p>
Navigate to "Control Panel and click on "Programs".
<p>
<img width="590" height="445" alt="Step_8_Windows_Features_On_Off" src="https://github.com/user-attachments/assets/eee7d2b0-3dda-45c7-858d-2f6bfb40aaa2" />
</p>
As highlighted. Selected "Turn Windows Features On or Off".
<p>
<img width="960" height="510" alt="Step_9_IIS_CGI" src="https://github.com/user-attachments/assets/22389104-9cb6-4f48-ace0-d85fb62070f6" />
</p>
Select "Internet Information Services" and make sure it is checked off properly we are then going to navigate to "World Wide Web Services" > "Application and Development Features" > Turn on "CGI. Then click "OK" to continue.
<p>
At this point "Internet Information Services" should be turned on successfully
</p>
<img width="960" height="510" alt="Step_11_Rewrite_Module_Install" src="https://github.com/user-attachments/assets/b292b3d0-6e90-4629-ac85-6d388c44156d" />
</p>

<h2>Step 3, Install Packages in osTicket Download Folder</h2>
<p>
Install the Rewrite Module. Right click and "Run as Admin". Accept the license terms and click "Next".
<p>
<img width="960" height="510" alt="Step_11_Rewrite_Module_Install_2" src="https://github.com/user-attachments/assets/b97aabfb-5827-48ef-ac18-6076a2faeed1" />
</p>
Run the installer and click "Finish" When it is complete.
<p>
<img width="960" height="510" alt="Step_12_VC_Redist_Install" src="https://github.com/user-attachments/assets/46f90fe8-c1ae-409b-8f89-d96ce1bce0ef" />
<p>
Install VC_redist.x86. osTicket requires the proper virtual redistribution packages to be installed to run correctly. Agree to the license terms and run the installer.
<p>
<img width="960" height="510" alt="Step_12_VC_Redist_Install_Success" src="https://github.com/user-attachments/assets/684c497d-c136-4eeb-9f66-caf621334d2b" />
<p>
Should be a fairly quick install and once complete click "Finish" to exit.
<p>
<img width="952" height="488" alt="Step_13_Extract_PHP" src="https://github.com/user-attachments/assets/f8075560-dc5b-4285-9127-be32f6806de7" />
</p>
Next we need to extract the PHP folder to the proper location on the C: drive. Navigate to it as shown and create the folder labeled "PHP" as shown.
<p>
<img width="956" height="536" alt="Step_14_Extract_Upload_to_Root" src="https://github.com/user-attachments/assets/be5730b8-5430-427f-aaad-fd75929701a5" />
</p>
We have another folder that we need to extract. This time we need to extract the osTicket-v1.15.8 folder. After that has been extracted we need to move the upload file that is there to "wwwroot" location on the C: drive as shown. Once that folder is extracted. Rename it to "osTicket" exactly as shown.
<p>
<img width="960" height="540" alt="Step_15_Install_MYSQL" src="https://github.com/user-attachments/assets/d2c939d7-6e3d-4740-822e-02ed04a0a7a7" />
</p>
osTicket requires a proper SQL server database running to store information correctly. Navigate to our osTicket download folder and run the MYSQL installer next.
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_2" src="https://github.com/user-attachments/assets/8325041c-5309-410e-ae69-a1c5b6090e71" />
</p>
Accept the license agreement and click "Next".
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_3" src="https://github.com/user-attachments/assets/ba7e353d-acbb-4852-8370-e43d6c929af3" />
</p>
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_3" src="https://github.com/user-attachments/assets/74fbc0eb-05f1-4dfb-a2b2-05f0d0b43555" />
<p>
Select "Typical" for the install variation and click "Next".
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_4" src="https://github.com/user-attachments/assets/4f2f84ba-a31b-455d-a216-d1b0c22b7777" />
</p>
Click "install" to finish the installation process for MYSQL.
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_5" src="https://github.com/user-attachments/assets/8d2de2e5-6972-49c5-8548-253b95db6d4e" />
</p>
Complete the MYSQL install and now select "launch configuration wizard" option as we have some more to finish setting up for the SQL server.
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_Configure" src="https://github.com/user-attachments/assets/09d98a73-046c-46a6-8e53-4afa68cd39c7" />
</p>
Now that we are in the config wizard. We want to select "Standard Configuration" and click "Next".
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_Configure_1" src="https://github.com/user-attachments/assets/d14b6272-a22d-4225-9931-a9ab1a8097e3" />
</p>
Select  "Install as Windows Service" we can just the leave the default name as shown and click "Next".
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_Configure_2" src="https://github.com/user-attachments/assets/52e61c77-d685-47df-bec2-88978445d15f" />
</p>
The config wizard is now ready to go! Click "Execute" to finish setting up the configuration wizard.
<p>
<img width="960" height="510" alt="Step_15_Install_MYSQL_Configure_3" src="https://github.com/user-attachments/assets/99e7009d-5cdd-4630-a15f-ada7c62da0a5" />
</p>
The configure wizard should be complete at this point! Nice, we can now close out of this step.

<h2>Step 4 Finish setting up the PHP Server</h2>
<p>
<img width="960" height="540" alt="Step_16_Run_IIS" src="https://github.com/user-attachments/assets/3bd091c3-45d7-4982-a8a3-bc3e1ea640f2" />
</p>
Next we need to run "Internet Information Services" as Administrator. Search for it and right click on the program to do so.
<p>
<img width="960" height="510" alt="Step_16_IIS_PHP_Manager" src="https://github.com/user-attachments/assets/a5536cf1-4439-4529-8ba0-47355e12f96f" />
<p>
We need to navigate to PHP manager for our Default site next.
<p>
<img width="960" height="510" alt="Step_17_New_PHP_Version" src="https://github.com/user-attachments/assets/f76c68b3-4728-464e-b4e2-155f8147283b" />
<p>
Time to register that new PHP version that we downloaded and shifted over to our C: drive! Click "Add new PHP version".
<p>
<img width="960" height="510" alt="Step_17_New_PHP_Version_2" src="https://github.com/user-attachments/assets/8a77f61b-5c1c-47e9-8f18-a7d657ceb825" />
<p>
Navigate to your PHP folder and select the following "php-cgi" file and click "Open".
<p>
<img width="960" height="510" alt="Step_17_New_PHP_Version_3" src="https://github.com/user-attachments/assets/ab3809a4-5af0-45eb-a300-c1c835ac3665" />
<p>
Double check you have the right file and click "OK" to continue adding the file. You are now down adding the PHP version we need.
<p>
<img width="960" height="510" alt="Step_18_Enable_PHP_Extensions" src="https://github.com/user-attachments/assets/8bc11c84-cd9b-487d-ad83-e224a50ef4e8" />
</p>
Next, we need to enable some extensions now for our ticketing system to work correctly in PHP manager. Navigate on the right to your "Default Site", select it and find PHP Manager. Then select "Enable Extensions" near the bottom.
<p>
<img width="960" height="510" alt="Step_18_Enable_PHP_Extensions_2" src="https://github.com/user-attachments/assets/70b383e0-2656-4374-8204-3b93df94adfe" />
</p>
Enable the following extensions that are highlighted above.* We are now done with setting the PHP version for osTicketing system.
<p>
<img width="960" height="510" alt="Step_16_Stop_Server" src="https://github.com/user-attachments/assets/f9edcda2-c44b-4df9-b8e6-9e7e462ab015" />
</p>
We are going to refresh the server and restart it to reflect the changes we have made already. We are going to click "Stop".
<p>
<img width="960" height="510" alt="Step_16_Start_Server" src="https://github.com/user-attachments/assets/3ba3c140-ccb8-4ba4-9e64-6cc85769a745" />
</p>
and then follow up with starting the server again!
<p>
<img width="960" height="510" alt="Step_19_rename_ost_config" src="https://github.com/user-attachments/assets/e8d223ee-7f06-40c9-abc8-dc10730e5dcf" />
</p>
Exit out of IIS for the time being. Navigate to your C: Drive > inetpub > wwwroot > osTicket> include location. We need to rename the file called "ost-sampleconfig.php" to exactly the name highlighted above "ost-config.php". Next we are going to change this files permissions to make it easier to access.
<p>
<img width="960" height="510" alt="Step_19_ost_config_advanced" src="https://github.com/user-attachments/assets/56f48301-4f78-4dce-96b4-633e3a811fff" />
</p>
Right click on the "ost-config.php" file and navigate to the "Security" tab. Then click on the "Advanced" icon.
<p>
<img width="960" height="510" alt="Step_20_disable_inheritance_permissions" src="https://github.com/user-attachments/assets/7c3ce3ea-5472-40f9-8e10-9ec8ec3284ca" />
</p>
We now want to "disable inheritance" to remove the default permissions the file has.
<p>
<img width="960" height="510" alt="Step_20_disable_inheritance_permissions_2" src="https://github.com/user-attachments/assets/875a18da-91e3-4bac-a2ba-b081ebd09fcb" />
</p>
Now that we have removed all the default users listed that had permissions. We want to click on "Add".
<p>

</p>







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
Fairly straight forward! All you have to do is go to "Admin Panel" in the top right. Once there, Click "Settings" then go to "Company". Under the "Company" tab you will see the tabs "Logos" and Backdrop". You can navigate to those tabs respectively to change your branding to change up from the generic ticketing setup.
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
I wanted to have a little variety of issues to choose from if a client were to reach out for assistance using the platform. The topics I included in the ticketing system are listed below:
</p>
<img width="1920" height="1080" alt="Help_Topics_Paddy&#39;s_Repairs" src="https://github.com/user-attachments/assets/ce160d3e-e2ad-4c02-87c4-556649dca080" />
</p>
<br />
<h2>Working Ticket Cycle Example 1 "Prof Oaks Business Critical Network Issue"</h2>
</p>
The first ticket example I "worked" was pretending that Prof Oak of the Kanto region had a "Business Critical" network outage at the lab... with a straight forward fix to the issue!
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
