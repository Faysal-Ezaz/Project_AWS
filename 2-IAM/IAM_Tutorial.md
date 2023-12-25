This is an easy IAM tutorial where we will be creating 2 users namely "User1" and "User2", but there is a catch, using the root user, we create 'User1' then using 'User1' we create "User2" and assign it to a Group.
Firstly, using the Root User, we create "User1". 
Then we shall create a group and assign the admin permission to the group. (While creating user, we get an option to create the group).
After creating the group, we assign "User1" to this group, hence granting 'User1' admin access. 
Then, we log into the IAM account 'User1'. 
We then create "User2". (If we are able to do this step, it shall give us the confirmation that 'User1' has been given the admin access). 
We then assign admin access to 'User2' (i,e. we add 'User2' to the admin group). 
We then log into IAM account "User2" and verify if 'User2' has the admin access. 

Now, there are a few terminologies that we have used, 
Policy : The JSON documents that are assigned to the Users or groups. (Policies define the permission to the users). 
Permissions : Permission are used in poicies, they decide whether 
Roles : 
Step 1) Firstly we log into the AWS root user console. 
