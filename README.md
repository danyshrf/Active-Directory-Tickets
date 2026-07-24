# Active Directory Support Ticket Examples
#### The Goal: To show hands-on experience solving the most common daily IT support tickets using Windows Server 2022 and Active Directory.

## Ticket 1: The Locked-Out User
### The Issue: A user came back from the weekend, forgot their password, guessed wrong three times, and got completely locked out of their computer.
### What I Checked: I looked up their username in Active Directory Users and Computers (ADUC) to confirm the account was actually locked due to our security rules.
### How I Fixed It:
- I opened their account properties in ADUC and went to the Account tab.
- I checked the "Unlock account" box and saved it.
- I asked the user to try logging in again, and they got in successfully.
- Screenshot:


## Ticket 2: Network Drive "Access Denied"
### The Issue: A new HR employee tried to open the \\Server\HR_Confidential shared folder but got an "Access Denied" pop-up on their screen.
### What I Checked: I checked the folder's security settings and saw it was restricted to the GRP_HR_ReadWrite group. Then, I checked the user's profile in ADUC and saw they hadn't been added to that group yet.
### How I Fixed It:
- I added the user to the GRP_HR_ReadWrite group in ADUC.
- Since permissions update when a user logs in, I asked them to log out and log back in.
- After that, they were able to open the folder and access the files without any issues.
- Screenshot:

## Ticket 4: Urgent Employee Offboarding
### The Issue: HR sent an urgent message that an employee left the company suddenly, and we needed to cut off their system access immediately to protect company data.
### What I Checked: I pulled up their account in ADUC to see exactly what department groups and files they currently had access to.
### How I Fixed It:
- First, I right-clicked their account and hit "Disable Account" so they couldn't log in anymore.
- Next, I removed them from all their department security groups.
- Finally, I moved their account out of the active employee folder and into a Disabled_Users folder to keep our system clean and organized.
- Screenshot:
