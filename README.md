# Active-Directory Lab

## Objective

## Table of Contents

- Add, modify, delete and disable a user in Active Directory.
- Find a user in our organization unit (OU) and unlock the account.
- Resetting a user's password.
- Managing various computers
- Add an organizational unit (OU) in the domain.
- Delete an OU from our domain using advanced features.
- Using Delegation Control and configuring PowerShell to see if it works.
- Changing the Group Policies.
- Creating new Group Policy Objects.

## Add, Modify, Disable and Delete a user in Active Directory.

The first thing every Help Desk user should know is how to do the basics in Active Directory. Adding a user, modifying their properties, deleting a user from their group and disabling an account.

# Add a User
 
 We have an Organizational Unit named Marketing that has the user Mark working in that department. Because the company is growing, more help is required for Mark. For that, the company has hired Terry Jones. We need to add Terry Jones to the Marketing team. 
 
<img width="720" height="701" alt="Adding new user to help mark" src="https://github.com/user-attachments/assets/502e5548-f580-4148-b026-4c6f5591ae6b" />

- To add Terry, we simply right click on the Marketing Organizational Unit (OU) and go to navigate to New then User.


<img width="440" height="380" alt="New user popup" src="https://github.com/user-attachments/assets/5fbe0cf7-10e1-4307-9b9d-af2cf7da1b50" />

- A new window will pop up, prompting us to add details of the new user. Not all the information is required but to avoid any confusion or security breaches, we want to enter every detail that is given.


<img width="444" height="376" alt="created base info for terry" src="https://github.com/user-attachments/assets/e72f10c0-8fe9-41a6-ba11-3b2aa7a21cf5" />

- Here I have added Terry Jones and entered a user logon name for him for his workstation, we then click “Next” to bring up the password page.


<img width="441" height="383" alt="given a base password must change it later" src="https://github.com/user-attachments/assets/2a776cf9-5738-4118-b0e6-4fa2c4ba4096" />

- Since it will be Terry's first time joining the company, he will need to create his own password. We will enter a base password for Terry to use, just so he can access the workstation first, the key step here is to make sure to have the "User must change password at next logon" is CHECKED. This step will prompt Terry to create a new password that is unique to him only, one that aligns with the Group Policies and will not be easily attainable by others.


<img width="442" height="383" alt="final" src="https://github.com/user-attachments/assets/23944cdd-0e22-454d-8e3a-05ee9f3012a4" />

- Once done, we get a final pop-up screen that shows all the changes we have done for the new user, we check to see if everything is correct and hit Finish.


<img width="819" height="830" alt="terry jones created and unlock account" src="https://github.com/user-attachments/assets/f2d6f430-3496-46d7-8983-5fc2815264d5" />

- As we can see, the user Terry Jones has been created in Marketing and will have access to only the Marketing deparment's data.

# Modify a User


# Disable a User

One of the biggest and worst mistakes an IT professional can make is leaving a user who is going through the offboarding process or has been terminated, active. Many companies receive various attackers and hackers in their network because more than 70% comes from human error, within the 70%, a vast majority is due to not properly disabling an account and assuming just deletion works. This can lead to ex-employees coming back for revenge for terminating them or for a hacker to see an open unused account and steal data that way as well.

<img width="627" height="487" alt="Disabling Christine Account" src="https://github.com/user-attachments/assets/216fe8dd-9b4c-4e9f-89a4-64989df3bfeb" />

- Here we have Christine in Sales that had recently quit from the company. To ensure that no unwanted access is being taken from her account, we would hit "Disable Account".

<img width="292" height="153" alt="popup for chrsitine" src="https://github.com/user-attachments/assets/bde061fa-fa5a-4626-a0b7-ac838e0a664c" />

- A small pop-up window shows up telling us that User Chrsitine has been disabled.

Now you may think, this sounds way too easy and pointless. But in real world, mistakes can happen, and most companies work in a fast-paced environment, so often IT professionals miss this crucial step, and it leads to disasters later. Also note, disabling a user is much better than just deleting them. For example, if Christine was the Senior Sales Manager and her workstation had some important data that Robert, Sophie and Thomas needed, then they could later ask the IT department to retrieve those files for them rather than panicking on what to do. 

# Delete a User














