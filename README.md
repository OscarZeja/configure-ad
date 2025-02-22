<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Part 1: Install Active Directory
	1.	Log In to DC-1
Start by logging into the server named DC-1. This is where we’ll set up Active Directory.
	
	2.	Install Active Directory Domain Services
Go to the server settings and install the tool called Active Directory Domain Services (AD DS).
	
 3.	Promote DC-1 as a Domain Controller (DC)
During the setup, create a new “forest” for your domain. Think of a forest as a big network that connects everything together. For example, use the name mydomain.com (or choose your own name—just remember it!).
	
 4.	Restart and Log Back In
Once DC-1 is set up, restart it and log in again using this format for the username: mydomain.com\labuser.


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


Part 2: Create a Domain Admin User
	1.	Open Active Directory Users and Computers (ADUC)
This is the tool where you manage users and groups in your domain.
	2.	Create Organizational Units (OUs)
OUs are like folders to organize users. Create these two OUs:
	•	_EMPLOYEES: For general users.
	•	_ADMINS: For admin users.
	3.	Add a New Admin User
	•	Inside the _ADMINS folder, create a user named Jane Doe with the username jane_admin and password Cyberlab123!.
	•	Add jane_admin to the Domain Admins group. This gives Jane full admin permissions.
	4.	Log In as Jane Doe
Log out of DC-1, then log back in using Jane’s account: mydomain.com\jane_admin. From now on, use this account as your admin user.

Part 3: Join Client-1 to the Domain
	1.	Set DNS Settings (Already Done)
Client-1’s DNS settings should already point to DC-1’s private IP address in the Azure Portal.
	2.	Restart Client-1 (Already Done)
This ensures the settings are applied.
	3.	Log In to Client-1
Use the local admin account (e.g., labuser) and join Client-1 to the domain mydomain.com. Once joined, the computer will restart.
	4.	Verify in ADUC
On DC-1, open ADUC and make sure Client-1 is listed as part of the domain.
	5.	Organize in an OU
Create a new OU named _CLIENTS in ADUC and move Client-1 into this folder.

And that’s it! You’ve successfully set up a domain, created an admin account, and connected a client to the domain. Now you’re ready to manage users and devices within your network!</p>
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
