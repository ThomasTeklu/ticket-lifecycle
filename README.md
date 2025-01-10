<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Ticket Lifecycle: Intake Through Resolution</h1>

This tutorial outlines the lifecycle of a ticket from intake to resolution within the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computing/Networks & IP Addresses)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

# Ticket Lifecycle Stages

- Intake
- Assignment and Communication
- Working the Issue
- Resolution

<h2>Review</h2>

In the previous installation of this series, we become a bit more familiar with our ticketing system as we went about configuring various parameters relating to its use and functionality. In this last section, we will observe what stages a ticket goes through within a ticketing system from start to finish. We will make/create the tickets as end users, then observe and resolve them as help desk professionals/agents. Let's get started!

### *Small Prelimenary Step* 

For the sake of the rest of our exercise here, we need to adjust one minor thing before we really get started. Log in as an admin through the Admin Login Page (http://localhost/osTicket/scp/login.php). From within the Admin Panel, go to Departments. Select the Maintenance Department by selecting the check box next to its name. While the Maintenance Department is selcted, click on the "More" button with the spoke next to it. From there select "delete" (NOT ARCHIVE). Confirm your decision then log out to move on to the next step.

# Intake

Recall in the last section, we created "users" (i.e. those who would be able to file complaints as tickets). The first step for us now will be to go to the end-user page (http://localhost/osTicket) and create a ticket using one of the user accounts that we created. Click on the "Open a New Ticket" button.

![image](https://github.com/user-attachments/assets/0df7d6c0-64bf-4041-af6f-be3658f027fb)

Fill in the blank fields as required. For the scenario of our ticket, we're going to imagine that the mobile banking system of our organization has become inaccessable. The most accurate Help Topic for a situation like this would be "Report a Problem / Business Critical Outage", however in order that this ticket be more realistic, we're going to assume that the end user doesn't exactly know the best way to classify their problems, and just enter it under "Report a Problem".

![image](https://github.com/user-attachments/assets/60dfe05d-9cde-42ca-8b41-968cc48ff2e4)

In keeping with the "untrained end user" veneer of this ticket, let's assume that the issue summary given is the following:
"entire mobile/online banking system is down"

![image](https://github.com/user-attachments/assets/121ed1ee-0804-43a0-9965-a3ae1aa31a41)

Now you can submit your ticket. You should see a response page stating that your ticket has been submitted and that you will receive a communication if needed.

# Assignment and Communication

Let's now move to the Admin/Analyst Login Page (http://localhost/osTicket/scp/login.php) and attempt to login as John Smith. Upon logging in, you should see the newly created ticket that we submitted through our user account. 

![image](https://github.com/user-attachments/assets/2e973165-8fc8-4062-b623-36ee2d1673e5)

Click on the ticket to open it and observe its properties. Look for specifically the "Priority", "Department", "SLA", and the "Assigned To". 

![image](https://github.com/user-attachments/assets/40c0736b-0c86-4cb9-b21f-c25c95c1dbd1)

These are all default settings based on ticket settings that can be managed from the admin account if desired. We'll leave those as they are for now, but we will edit the properties in this ticket from what they originally were. 

Observe that the SLA Plan is set to "Default SLA". Click on this and in the window that pops up, change it to "Sev-A" which was covered in the prior repository.

![image](https://github.com/user-attachments/assets/9d7ea2f6-acca-4c82-bb18-ffb551705022)

You'll notice that there is an section where you can provide an optional explanation as to why you are manually making this switch. While we won't leave one now, it is generally a good practice to provide context for all steps just to keep the ticket's history as clear as possible for anyone who may work on it at any given stage. 

In addition to the SLA Plan, we will also switch the Department. Click on "Support" and switch it to the "SysAdmins" department. 

### Question: What did you notice?

Upon switching the departments, was there any automatic reaction for you? If not, click on the "Tickets" tab and see if there's a difference. You should no longer be able to see the ticket! That's because, using the permissions associated with John's account, we sent the ticket to a department of which John is not a member. We'll have to continue working on this ticket with an account that is a member of the "SysAdmins" department:

![image](https://github.com/user-attachments/assets/3c318763-e91e-42ce-9938-ff4bd3588949)


# Working the Issue

Returning to the Agent Login Page, log in using the "Jane" account the you created in the last installation of the tutorial. Upon logging in, you should now see the transferred ticket.

![image](https://github.com/user-attachments/assets/d6b1beb3-729c-4127-be0f-11d73b67bf00)

Remember that Jane is a member of the SysAdmins department, so now that the ticket has been assigned to her department, she can view it immediately in her Tickets dashboard after logging in.

Open the ticket and scroll down to the Ticket Thread. Notice that you can see the full history of the ticket from its creation to the current moment.

![image](https://github.com/user-attachments/assets/00178f5b-b962-4d0f-b294-7d20e61c6dd7)

Now that we've observed the ticket briefly, let's move on to actually resolving it. It should be noted that the agent responsible for the ticket will often have to do some reading between the lines and also apply situational awareness to tickets since the descriptions that come with initial submissions can be vague. That being said, we will scroll down to the Post Reply section of the ticket. As a SysAdmin who has just been provided with a ticket (namely Jane), you will take steps on your side to resolving the issue while alerting the team as to what you are about to do. Within the Post Reply write:

"I suspect the issue might be with the recent updates. We tested them sufficiently, but I'll still look into them. If I determine that they were the issue, we'll get on to rolling them back".

Post this reply and observe as it gets added to the ticket's thread. 

![image](https://github.com/user-attachments/assets/d695ae0e-edd3-40a6-85d7-8d7824a015f2)

Since we don't have an actual organization that we work in to check if these said "updates" were the actual problem, we're just going to assume that they were, and that we checked the relevant back-end configuration to figure out as much. As Jane, go back to the Post Reply and let your team know the following:

"Determined that it was indeed the recent updates. We rolled them back, notified the vendor, and are currently awaiting a proper fix. For now, online banking should now be back up".

# Resolution

You've alerted everyone that the issue behind the ticket has been resolved. Now all that remains is to actually get rid of the ticket itself. Scroll back to where you can see the ticket's status. Click on "Open":

![image](https://github.com/user-attachments/assets/44b5cbf8-e850-4a6c-9851-8bdf1fb56b81)

After that, click on "Resolved", reflecting the nature of your ticket. In the window that pops up, click "Close". Your browser should now automatically refresh and you should be taken back to the ticket's homepage. Notice that since your only ticket has been resolved, you have nothing else there:

![image](https://github.com/user-attachments/assets/1f9350d8-440e-414b-8746-8f787d2c94ee)

# Conclusion

Congratulations! You've just resolved a ticket and completed the osTicket tutorial. I hope that this was a helpful endeavor for you and that you learned something new. I would recommend re-doing this tutorial series multiple times over, each time decreasing the reliance upon my instructions so as to really master the skills developed here. Wishing you all the best!

