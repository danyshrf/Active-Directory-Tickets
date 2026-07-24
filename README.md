# Active Directory Support Ticket Examples
#### The Goal: To show hands-on experience solving the most common daily IT support tickets using Windows Server 2022 and Active Directory.

## Ticket 1: The Locked-Out User
### The Issue: A user came back from the weekend, forgot their password, guessed wrong three times, and got completely locked out of their computer.
### What I Checked: I looked up their username in Active Directory Users and Computers (ADUC) to confirm the account was actually locked due to our security rules.
### How I Fixed It:
- I opened their account properties in ADUC and went to the Account tab.
- I checked the "Unlock account" box and saved it.
- I asked the user to try logging in again, and they got in successfully.
Screenshot:
