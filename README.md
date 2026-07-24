# Active Directory Support Ticket Examples
#### The Goal: To show hands-on experience solving the most common daily IT support tickets using Windows Server 2022 and Active Directory.

## Ticket 1: The Locked-Out User
### The Issue: A user came back from the weekend, forgot their password, guessed wrong three times, and got completely locked out of their computer.
### What I Checked: I looked up their username in Active Directory Users and Computers (ADUC) to confirm the account was actually locked due to our security rules.
### How I Fixed It:
- I opened their account properties in ADUC and went to the Account tab.
- I checked the "Unlock account" box and saved it.
- I asked the user to try logging in again, and they got in successfully.
- Screenshot: ![Checking the unlock account box in ADUC](1-Account_unlocking.png)
- ![Checking the unlock account box in ADUC](ticket1-lockout.png)


## Ticket 2: Network Drive "Access Denied"
### The Issue: A new HR employee tried to open the \\Server\HR_Confidential shared folder but got an "Access Denied" pop-up on their screen.
### What I Checked: I checked the folder's security settings and saw it was restricted to the GRP_HR_ReadWrite group. Then, I checked the user's profile in ADUC and saw they hadn't been added to that group yet.
### How I Fixed It:
- I added the user to the GRP_HR_ReadWrite group in ADUC.
- Since permissions update when a user logs in, I asked them to log out and log back in.
- After that, they were able to open the folder and access the files without any issues.
- Screenshot:

## Ticket 3: Day-One Password Reset
### The Issue: A brand-new employee forgot the temporary password we gave them and couldn't log into their workstation on their first day.
### What I Checked: I quickly verified with HR that this was indeed the correct user requesting the reset to ensure security.
### How I Fixed It:
- I found their profile in ADUC, right-clicked, and selected "Reset Password."
- I gave them a new temporary password.
- I made sure to check the box that says "User must change password at next logon." This forced them to create their own private password immediately upon logging in.
- Screenshot:
![Reset password screen with the force change box checked](ticket3-password.png)

## Ticket 4: Urgent Employee Offboarding
### The Issue: HR sent an urgent message that an employee left the company suddenly, and we needed to cut off their system access immediately to protect company data.
### What I Checked: I pulled up their account in ADUC to see exactly what department groups and files they currently had access to.
### How I Fixed It:
- First, I right-clicked their account and hit "Disable Account" so they couldn't log in anymore.
- Next, I removed them from all their department security groups.
- Finally, I moved their account out of the active employee folder and into a Disabled_Users folder to keep our system clean and organized.
- Screenshot:

## Ticket 5: Broken Trust Relationship (PC lost connection to the server)
### The Issue: A user came back from a month-long vacation, and their computer wouldn't let them log in, showing the error: "The trust relationship between this workstation and the primary domain failed."
### What I Checked: I pinged the server from their PC to make sure the internet and network cables were working. The issue was just that the PC had been offline for so long, it lost its secure sync with Active Directory.
### How I Fixed It:
- I logged into their computer using the local admin account.
- I disconnected the PC from the domain (putting it in a Workgroup) and restarted the computer.
- Then, I rejoined the PC back to the domain using my admin credentials and restarted it one last time. The user was then able to log in normally.
- Screenshot:
