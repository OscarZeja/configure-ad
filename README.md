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


<h2>Deployment and Configuration Steps</h2>



![Screenshot 2025-02-27 205747](https://github.com/user-attachments/assets/e1894aa2-087b-451f-850b-19f02e2dedd0)



Part 1: Install Active Directory
	
 1.	Log In to DC-1
Start by logging into the server named DC-1. This is where we’ll set up Active Directory.
	
 2.	Go to the server settings and install the tool called Active Directory Domain Services (AD DS). Install Active Directory Domain Services. 
	
 4.	Promote DC-1 as a Domain Controller (DC)
During the setup, create a new “forest” for your domain. Think of a forest as a big network that connects everything together. For example, use the name mydomain.com (or choose your own name—just remember it!).
	
 5.	Restart and Log Back In
Once DC-1 is set up, restart it and log in again using this format for the username: mydomain.com\labuser.


![Screenshot 2025-02-27 211953](https://github.com/user-attachments/assets/8ea254c9-5f2b-41f9-a04d-9e1dec2f84e0)



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


![Screenshot 2025-02-27 212347](https://github.com/user-attachments/assets/247181f2-10a0-4bc6-b5b4-a8aff24b926f)



Part 3: Join Client-1 to the Domain
	
	
1.	Log In to Client-1
Use the local admin account (e.g., labuser) and join Client-1 to the domain mydomain.com. Once joined, the computer will restart.
	
2.	Verify in ADUC
On DC-1, open ADUC and make sure Client-1 is listed as part of the domain.
	
3.	Organize in an OU
Create a new OU named _CLIENTS in ADUC and move Client-1 into this folder.

And that’s it! You’ve successfully set up a domain, created an admin account, and connected a client to the domain. Now you’re ready to manage users and devices within your network!</p>
<br />
