# Active-Directory Lab

## Objective
The Active Directory Lab aims to establish a hands-on experience with core identity and access management tasks using Active Directory in a Windows environment. The primary focus is to practice real-world administration tasks, including managing users, computers, Organizational Units (OUs), delegation, and Group Policy. 

The end goal of this lab is to simulate system administration and IAM responsibilities by securely managing identities, enforcing policies, and applying the principle of least privilege. These tasks demonstrates practical Active Directory skills that are suitable for help desk, system administration and IAM-focused roles.

## Table of Contents

- Add, modify, delete and disable a user in Active Directory.
- Find a user in our organization unit (OU) and unlock the account.
- Resetting a user's password.
- Managing computers.
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

For deleting a user, it works the same way. First, we must always disable the account first before anything else. This ensures that important things like credentials, group memberships and access tokens are take away from the user when not in use.

And you may ask why should be delete an account if disabling is an option. Well to simplify, it’s to declutter the Active Directory. You could have 50-100 accounts in the OU of Sales and a new hire like Lisa Ann could have a similar name to ex-employee Lisa Annabell, this could lead to IT professionals thinking Lisa Annabell is an active employee and accidentally give her permission to confidential company data. 

Access control records and following compliance controls are one of the biggest things companies must follow (SOX, HIPPA, NIST) and by following this good practice leads to maintaining security, reduce attack surfaces and keeping the directory clean




# Find a user in (OU) and unlock the account.


<img width="720" height="653" alt="Finding robert from OU" src="https://github.com/user-attachments/assets/ebabcbb6-e5f5-492f-b84c-033b5f2053f0" />

- Say we have various Organizational Units called IT, Management, Marketing, R & D, Sales, and Students. And we need to find Robert because he accidentally locked his account.

- Rather than clicking each OU one by one and scrolling till you find Robert, you can use the find feature to find the Robert you are looking for. *NOTE: make sure you right click on the main OU to look through all the OUs, if you right-click on sales or IT, it will search through users in that specific department only. *


<img width="520" height="508" alt="Finding robert" src="https://github.com/user-attachments/assets/53804922-7718-44b8-96e2-231f51f8bfe6" />

- We can then find Robert by typing in his name at the top and clicking "Enter" or "Find Now". A list of the results will show up at the bottom and you can find the correct person. *NOTE: mine only says Robert but in a real world scenario, typing in the full name is better to ensure the right person is being found*


<img width="415" height="540" alt="Robert Properties" src="https://github.com/user-attachments/assets/189f7e0e-8605-407b-b09a-fa421cc129d6" />

- Once you click on Robert a new page will pop-up, this page is where all of Robert’s properties are, what membership he has, his general information, account name, description, profile, etc. Notice under Account, you can see the unlock account is unchecked, only uncheck this when you can verify that the right user is by his workstation.


<img width="415" height="540" alt="Unlock Robert&#39;s account" src="https://github.com/user-attachments/assets/4252d888-35b5-4d5f-9075-b1d08c2f0a3c" />

- Once we have selected the unlock account, we must also ensure that the "User must change password at next logon" is also checked. Robert may have locked his account for entering the wrong password too many times and the Group Policy may have been trigged, this will allow Rober to choose and new password and hopefully he remembers this one better.




# Resetting a user's password.


<img width="520" height="508" alt="Finding robert" src="https://github.com/user-attachments/assets/0113cd3c-6f70-473d-aa4d-a961fb6815ad" />

- You can reset a user's password in many ways, but this method is the best in my opinion just to ensure that you are modifying the right person's properties. You would first want to find the user like we did earlier.


<img width="520" height="557" alt="Reset Robert Password" src="https://github.com/user-attachments/assets/5056a350-d8f9-49be-a985-89b172a4b9ad" />


- Instead of clicking on Robert and pulling up his full properties, we can right click on his name and navigate to "Reset Password".


<img width="530" height="510" alt="Window pops up for password reset" src="https://github.com/user-attachments/assets/24e377bb-ad5e-47a6-8f72-4d1bfecbaf53" />

- A new pop-up window will show again, and it will prompt us to reset the password for Robert. Make sure you do something simple for Robert since he will need to change the password to something that is unique to him only.


<img width="517" height="511" alt="New password for robert and unlocks account" src="https://github.com/user-attachments/assets/8191a0ee-8723-4512-acd3-9722bfd475ec" />

- Once you have entered the simple password, ensure that the "User must change password at next logon" is checked (Not optional). Even though it says Account Lockout Status on this Domain Controller: Unlocked, I still checkmark it just to avoid any more confusion (Optional). Click Ok and make sure Robert is able to access his workstation properly.


# Managing computers
**In Progess**

