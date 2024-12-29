<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Ticket Lifecycle: Intake Through Resolution</h1>
This tutorial outlines the lifecycle of a ticket from intake to resolution within the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Ticket Lifecycle Stages</h2>

- Intake
- Assignment and Communication
- Working the Issue
- Resolution

<h2>Lifecycle Stages</h2>

As stated above, in this last section we will observe what stages a ticket goes through within a ticketing system from start to finish. We will make/create the tickets as end users, then observe and resolve them as help desk professionals/agents. Let's get started!

### Small Prelimenary Step

For the sake of the rest of our exercise here, we need to adjust one minor thing before we really get started. Log in as an admin through the Admin Login Page (http://localhost/osTicket/scp/login.php). From within the Admin Panel, go to departments. Select the Maintenance Department by selecting the check box next to its name. While the Maintenance Department is selcted, click on the "More" button with the spoke next to it. From there select "delete" (NOT ARCHIVE). Confirm your decision then log out to move on to the next step.




## Intake

Recall in the last section, we created "users" (i.e. those who would be file complaints as tickets). The first step for us now will be to go to the end-user page (http://localhost/osTicket) and create a ticket using one of the user accounts that we created. Click on the "Open a New Ticket" button.

![image](https://github.com/user-attachments/assets/63df822f-a684-45f5-a881-37dc933d7d20)

Then fill in the blank fields as required. For the scenario of our ticket, we're going to imagine that the mobile banking system has become inaccessable. The most accurate Help Topic for a situation like this would be "Report a Problem / Business Critical Outage", however in order that this ticket be more realistic, we're going to assume that the end user doesn't exactly know the best way to classify their problems, and just enter it under "Report a Problem".

![image](https://github.com/user-attachments/assets/c4a4d3e7-48b5-4224-9401-c64fd409ffd0)

In keeping with the "untrained end user" veneer of this ticket, let's assume that the issue summary that they enter is the following:
    "entire mobile/online banking system is down"


![image](https://github.com/user-attachments/assets/1f791c97-cdce-4334-b7be-156524551bec)


Now you can submit your ticket. You should see a response page stating that your ticket has been submitted and that you will receive a communication if needed.



## Assignment and Communication

Let's now move to the Admin/Analyst Login Page (http://localhost/osTicket/scp/login.php) and attempt to login as John Smith. Upon logging in, you should see the newly created ticket that we submitted through our user account. 

![image](https://github.com/user-attachments/assets/1317c661-18db-46f3-a78e-35d4b3f834f0)

Click on the ticket to open it and observe its properties. Look for specifically the "Priority", "Department", "SLA", and the "Assigned To". 

![image](https://github.com/user-attachments/assets/e6da54a3-bd18-44a3-a569-33cece618893)

These are all default settings based on ticket settings that can be managed from the admin account if desired. We'll leave those as they are for now, but we will edit the properties in this ticket from what they originally were. 

Observe that the SLA Plan is set to "Default SLA". Click on this and in the window that pops up, change it to "Sev-A" which we was covered in the prior repository.

![image](https://github.com/user-attachments/assets/a1accf38-7dc4-4f94-bf84-f84aee4e6fa2)

You'll notice that there is an section where you can provide an optional explanation as to why you are manually making this switch. While we won't leave one now, it is generally a good practice to provide context for all steps just to keep the the ticket's history as clear as possible for anyone who may work on it at any given stage. 


In addition to the SLA Plan, we will also switch the Department. Click on "Support" and switch it to the "SysAdmins" department. 

### Question: What did you notice?

Upon switching the departments, was there any automatic reaction for you? If not, click on the "Tickets" tab and see if there's a difference. You should no longer be able to see the ticket!


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
