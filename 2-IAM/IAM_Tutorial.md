## <b>Objective</b> of this Mini-Project:  
This is an easy IAM tutorial where we will be creating 2 users namely "User1" and "User2", but there is a catch, using the <b>root user</b>, we create 'User1' then using 'User1' we create "User2" and assign it to a Group.    

## Explaination of the problem statement: 
Firstly, using the <b>Root User</b>, we create "User1".  
Then, we shall create a <i>group</i> and assign the <b>'Admin Permission'</b> to the group. (While creating user, we get an option to create the group).  
After creating the group, we assign "User1" to this group, hence granting 'User1' admin access.   
Then, we log into the IAM account 'User1'.   
We then create "User2". (If we are able to do this step, it shall give us the confirmation that 'User1' has been given the admin access).   
We then assign admin access to 'User2' (i,e. we add 'User2' to the admin group).   
We then log into IAM account "User2" and verify if 'User2' has the admin access. 

## Explaination of the terminologies used: 
Now, there are a few terminologies that we have used,   
<ul>
  <li><b>Policy</b> : The JSON documents that are assigned to the Users or groups. (Policies define the permission to the users).</li>
  <li><b>Permissions</b> : Permission are used in poicies, they decide whether</li>
  <li><b>Roles</b> :</li>
</ul>  

## Steps to be followed: 
<b>Step 1)</b> Firstly we log into the AWS root user console. 
