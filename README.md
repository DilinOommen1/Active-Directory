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

- As we can see, the user Terry Jones has been created in Marketing and will have access to only the Marketing department's data.

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

- Rather than clicking each OU one by one and scrolling till you find Robert, you can use the find feature to find the Robert you are looking for. *NOTE: make sure you right click on the main OU to look through all the OUs, if you right-click on sales or IT, it will search through users in that specific department only*.


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

<img width="840" height="531" alt="all comp, server and others together, no good" src="https://github.com/user-attachments/assets/508df1b7-ea0a-401d-8815-e55d4b9b116c" />

- Sometimes, small businesses and even larger scale businesses can have a clutter of PCs, laptops, servers and etc that are put into one container in the OU. This is usually not the best practice to have since some of these machines are directly connected to users in the company AND different workstations means having different policies than others including different privileges and having access to sensitive information.


<img width="228" height="368" alt="Added workstation and server OUs" src="https://github.com/user-attachments/assets/9e30cb5c-b305-4219-b620-7090ac98177e" />

- To fix this, figure out which machine is what. Are they directly connected to the user and are used for browsing/work activities or are they used to bring service among the devices? Here we have created 2 OUs, one for workstations for PCs and laptops, and one for servers for the servers that are connected to the network.



<img width="782" height="564" alt="Moving all laptops and PC to workstation" src="https://github.com/user-attachments/assets/f060667f-fc02-4cc5-8985-31aa84412368" />

- Next, is to highlight all the machines that will go to workstations, we can easily do that by holding CRTL and clicking each laptop and PC that is in list. Make sure everything is highlighted correctly and ensure that the servers are not.
- Then right click and navigate to the Move tab, this will allow you to move all the machines highlighted to the designated OU that you desire.


<img width="403" height="386" alt="Popup for moving workstation" src="https://github.com/user-attachments/assets/03e49c4b-ab5a-427d-8c21-daebd2b34d2b" />

- Scroll down until you find workstations. An OU like this should usually be directly under the main domain because of the different Group Policies that it has. Click OK once you have highlighted Workstations as your designation.


<img width="870" height="482" alt="Results for workstation" src="https://github.com/user-attachments/assets/9a26960d-417f-4e00-a6b0-617b90af8b77" />


<img width="660" height="483" alt="Result for server" src="https://github.com/user-attachments/assets/bf834f5d-069c-4723-b4f9-3d09448510da" />

- And the result should be the Workstation OU having the laptops and PCs under it's control and the servers should be linked to the server OU as well. From here Active Directory admins should be able to change any Group Policies or update any worstations that it may need directly here without disrupting the other machines and OUs. 


# Add an organizational unit (OU) in the domain.

<img width="798" height="568" alt="Main OUs" src="https://github.com/user-attachments/assets/24230e14-832b-460b-a0cd-0fb54d14725b" />

- Your company already has various departments called IT, Management, Marketing, R & D and Sales. But now your company wants to make a whole new department dedicated to student workers that are interning and you are tasked to create a new OU just for them.

<img width="820" height="734" alt="how to create a new OU" src="https://github.com/user-attachments/assets/85a91ac2-0a00-44bb-b591-330c5095d424" />

- The first step in creating a new OU is to ensure you are under the Main OU as the rest of the departments, here it is labeled as THM. You do not want the Students department to have access to the entire domain of the company as those privileges are too high for interns. So, ensure that you are under the main OU that contains all the departments.

- Right click on main OU, navigate to New and find Organizational Unit.

<img width="774" height="647" alt="NEW OU POPup" src="https://github.com/user-attachments/assets/80a77662-a8b1-4254-818a-ca63da593f62" />

- A pop-up like this will appear, prompting you to give a name for new OU that you are creating. Enter the name Students and hit OK when done.

<img width="790" height="348" alt="Created new OU students" src="https://github.com/user-attachments/assets/fd93d0e1-3b33-42bc-8f1f-e3d84b317609" />

- The result is a new OU called Students being created under the main OU. Now admins can effectively create new users under Students and have a new working department.


# Delete an OU from our domain using advanced features.

- Now the company finds that it is on a budget and must get rid of a department that is not needed anymore. They find employees in the Research and Development department have been either promoted or left the company completely and are finished with the offboarding process thus only having 1 person employed. We need to delete the OU Research and Development(R & D).


<img width="548" height="665" alt="Trying to delete an OU" src="https://github.com/user-attachments/assets/bd3647f1-42aa-41ad-8005-83a4506fe5eb" />

- Navigate to the R & D OU under the main OU (THM), right click on it and find the Delete option.

  
<img width="569" height="230" alt="Delete not working" src="https://github.com/user-attachments/assets/f236b058-ad35-45d2-b98f-e3fe62067ad0" />

- Once you click delete, you will get a pop-up that says, "you do not have sufficient privilege or object is protected. Since we are already the main admin for this Active Directory, we can safely assume that the R & D OU is protected from accidentally being deleted. This is a safeguard that is put into place automatically to prevent someone from deleting an important department and having to start over again.


<img width="575" height="393" alt="Advanced features" src="https://github.com/user-attachments/assets/85a0ff07-1e7f-4e8a-b499-d259f3754c7c" />

- Once we have confirmed with the higher ups that this is the right department we want to delete, we can go ahead and use the Advanced Features to continue with the process. To begin, click on the R & D department and navigate to the top of the screen and find View. *NOTE: BE SURE TO HIGHLIGHT THE RIGHT DEPARTMENT AND NOTHING ELSE TO ENSURE THE RIGHT OU IS BEING DELETED*. Find the option called Advanced Features and click on it.


<img width="753" height="747" alt="Unchecking projection box" src="https://github.com/user-attachments/assets/d2ce5a32-fa6e-4748-8e86-0e2753510fb3" />

- This will pull up the properties of R & D and should automatically bring up the object tab, if not do that now. A lot of information may be presented to you but the main thing we are looking for is an option at the end of the page called "Protect object from accidental deletion". If it has a check box next to it, uncheck it now. This allows us the admins to delete this specific OU only and prevent any errors from happening. Click OK when done.



<img width="761" height="411" alt="Deletion works" src="https://github.com/user-attachments/assets/56f54c9c-5842-4afd-b544-c94222b44398" />

- And as we can see, the deletion has worked, and the Research and Development department is gone.
-  *IMPORTANT:* As said before, make sure you take out anyone who is still active in the department. In this case Bob is still active, so he either needs to be transferred to a new department or be let go and disable his account/take away his privileges.




