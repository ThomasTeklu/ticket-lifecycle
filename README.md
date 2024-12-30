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

Upon switching the departments, was there any automatic reaction for you? If not, click on the "Tickets" tab and see if there's a difference. You should no longer be able to see the ticket! That's because, using the permissions associated with John's account, we sent the ticket to a department of which John is not a member. We'll have to continue working on this ticket with an account that is a member of the "SysAdmins" department.



# Working the Issue

Returning to the Agent Login Page, log in using the "Jane" account the you created in the last section of the tutorial. Upon logging in, you should now see the transferred ticket.

![image](https://github.com/user-attachments/assets/21548fe9-a738-41c2-85cc-38fb73b08ed1)

Remember that Jane is a member of the SysAdmins department, so now that the ticket has been assigned to her department, she can view it upon logging in.

Open the ticket and scroll down to the Ticket Thread. Notice that you can see the full history of the ticket from its creation to the current moment.


![image](https://github.com/user-attachments/assets/b8d9e880-2a54-4074-b5a6-c8ca44586d05)

**Note**: As you can see, due to the times at which I took these screenshots, there was enough of a period for my ticket to become overdue, which is why the prior image had a small icon along with the ticket name. This is by no means an indicator of what will happen to you. It all depends on the timeline by which you work all of this through. Continuing...


Now that we've observed the ticket briefly, let's move on to actually resolving it. It should be noted that the agent responsible for the ticket will often have to do some reading between the lines and also apply situational awareness to tickets since the descriptions that come with initial submission can be a vague. That being said, we will scroll down to the Post Reply section of the ticket. As a SysAdmin who has just been provided with a ticket (namely Jane), you will take steps on your side to resolving the issue while alerting the team what you are about to do. Within the Post Reply write:

"I suspect the issue might be with the recent updates. We tested them sufficiently, but I'll still look into them. If I determine that they were the issue, we'll get on to rolling them back".

Post this reply and observe as it gets added to the ticket's thread. 

![image](https://github.com/user-attachments/assets/04148a0f-3aa7-49d1-a069-87eabcf09c41)

Since we don't have an actual organization that we work in wherein we can check if these said "updates" were the actual problem, we're just going to assume that they were, and that we checked the relevant back-end configuration to know such. As Jane, go back to the Post Reply and let your team know that:

"Determined that is was indeed the recent updates. We rolled it back, notified the vendor, and are currently awaiting a proper fix. For now, online banking should now be back up".

# Resolution

You've alerted everyone that the issue behind the ticket has been resolved. Now all that remains is to actually get rid of the ticket itself. Scroll back upon to where you can see the status. Click on "Open":

![image](https://github.com/user-attachments/assets/eda5dc23-e4f8-42a7-abf0-c63ea687b6c7)

After that, click on "Resolved", reflecting the nature of your ticket. In the window that pops up, click "Close". Your browser should now automatically refresh and you should be taken back to the tickets homepage. Notice that since your only ticket has been resolved, you have nothing else there:

![image](https://github.com/user-attachments/assets/ae69ca80-57d3-4ccd-aa1b-730431a534ca)

Congratulations! You've just resolved a ticket and completed the osTicket tutorial that I have for you. Though I myself am a novice, I hope that this was a helpful endeavor for you and that you learned something new. Wishing you all the best!

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
