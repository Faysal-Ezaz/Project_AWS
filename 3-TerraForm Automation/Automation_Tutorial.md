This is a project where I shall be using <b>Terraform</b> to Automate the creation of an EC2 instance/instances.  
Pre-requisits:  
(a) <b>AWS IAM</b> and  
(b) <b>AWS EC2</b>. Please keep in mind that this will contain a detailed explaination of all the commands used and all the steps followed.  



<h2><a href = "https://releases.hashicorp.com/terraform/1.5.7/terraform_1.5.7_windows_386.zip">Software Requirements:</a></h2>   
Head over to this website to install Terraform (https://developer.hashicorp.com/terraform/downloads)  
Then install the following
  

![Screenshot (1352)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/c014ecc1-d2bf-4dd3-b0c0-0c45fc2c9766)  
Then we will head over to 'C' drive of our system and inside 'C' drive we open "Program Files".  
Inside 'Program Files', we will create a folder "terraform" and then unzip the previously downloaded software (terraform software).  
Next comes the part where we add the path for the software in system variables. For this we have to follow the steps:  

<ul>
  <li>Press on the windows key and type <b>Edit the System Environment Variable</b>.</li>
  <li>![image](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/74e42957-5368-4e52-a82a-e4a9ba0916cb)</li>
  <li>Under 'Advanced' the option <strong>"Environment Variables"</strong> appears, click on it. </li>  
  <li>Under 'User variables for new', we have to click on the option <strong>"Path"</strong> and then click on <b>'Edit'</b></li>  
  <li>It should look something like this: ![image](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/8b94140e-ffce-45f4-afb0-74dec447b931)</li>  
  <li>Then, the copied path to be pasted should look something like this: ![image](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/33ea6d59-3085-484e-93ab-4b8ec6baf49b)</li>  
  <li>Then click on 'ok' and we are basically done setting up the environment variable. </li>
</ul>  


<h2> Tools Required for this mini Automation Project:</h2>  
  a) Git Bash.  
  b) AWS Console.
    
  
<h2>Steps to install GitBash are as follows:</h2>  
<ul>
  <li>Head over to this website: (https://git-scm.com/download/win) and select the option <b>"64-bit Git for Windows Setup."</b></b></li>  
  <li>Otherwise click on this link for the direct installation: (https://github.com/git-for-windows/git/releases/download/v2.42.0.windows.2/Git-2.42.0.2-64-bit.exe)</li>
</ul>  
Also keep in mind that there is no requirement to add the path variable for GitBash like we did for Terraform!  


In order to validate that <b>terraform</b> has been installed properly and the path is working fine, we have to run the following commands in "GitBash"  

Open Gitbash and type the command: <b>terraform version</b>.  
If it appears just like the following, then we can be rest assured that our terraform and gitbash are working just fine.  

![Screenshot (1355)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/fea9807e-903a-45ae-a51d-95db44ab3cf3)

Now I am assuming you already have an AWS Account. So, we shall login to our respective AWS Accounts.  


<h2>The general workflow will be as follows:</h2> 
Firstly, we will create an IAM user, assign it the "AdministratorAccess" Role and finally create an "Access Key". More on <a href = "#section1"><b>Access Key</b></a> later on in this project and why it is actually used/needed. 
Secondly, we will open GitBash and type in some command, along with some code that will help us automate the entire process!  

<strong>Here are the commands that we will use in Gitbash.</strong>  
<strong>Basic Linux Commands to be used.</strong>
<ul>
  <li><strong>cd</strong>: This command is used to change directory. (Changing folders to be more precise 😅😅)</li>  
  <li><strong>mkdir</strong>: This will allow us to create a new folder!</li>  
  <li><strong>ls</strong>: This command helps us list all the files in the directory(folder).</li>  
</ul>  
<b>Terraform Commands to be used</b>  
<ul>
  <li><strong>vi</strong>: This command is used to create a new terrraform file and the extension of this file is <b>'.tf'</b>.</li>
  <li><strong>terraform init</strong>: This command is used to <i>set up</i> the Terraform backend, modules, and providers.</li>
  <li><strong>terraform plan</strong>: This command <i>creates an execution plan</i>, and lets us <i>preview</i> the changes that terraform will make to our infrastructure.</li>
  <li><strong>terraform validate</strong>: This command is used to <i>validate the syntax</i> of the terraform file. </li> 
  <li><strong>terraform apply</strong>: This command <i>carries out the planned changes</i> to each resource using the relevant infrastructure provider's API.</li> 
  <li><strong>terraform delete</strong>: This command <i>terminates resources</i> managed by our terraform project.</li>
</ul>  

Now, lets start with the hands-on: 

Step-1: Working with AWS IAM service. (we open aws console and type IAM on the search bar) 
a) Under <i>Access Management</i>, we click on <b>'Users'</b> and then, click on <b><b>"Create User"</b></b>.  
![Screenshot (1356)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/5c1d379f-c28d-4d25-86aa-3b908bcc7d2e)  

b) Under "User Details", we enter <b>GitTerraformUser</b> as the Username then click on <i>Next</i>.  
![Screenshot (1357)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/8035e173-0e30-4111-850e-9cb2bbbd431d)  

c) Under 'Permission Options', we have to click on the third option <b>Attach Policies Directly</b>.  
d) Under 'Permission Policies', we have to select <b>AdministratorAccess</b> and then click on <i>Next</i>  
![Screenshot (1358)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/84f1858e-ca7a-417c-9940-75713052bae6)  

e) Under <b>Review and Create</b>, click on <i>Create User</i>. And hence the user is created.   
![Screenshot (1361)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/2d5799c7-18f1-4fbd-a4ff-e213b0c25253)  

f) We have to create an <i>Access Key</i> for the 'User' for this, click on the 'GitTerraformUser' in the IAM Console.  
g) Then 'GitTerraformUser', click on <b>Create Access Key</b> under <i>Access Key 1</i>.  
![Screenshot (1362)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/24869030-6d93-4d41-8f3d-7a3c3100ad33)  

h) Then in the followup window, under <i>Access key best practices & alternatives</i>, select the 3rd option, click on the check-box and finally click on 'Next'.  
![Screenshot (1363)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/454b8d7d-1065-4d6f-ada1-ee31d7e0e23d)  

i) Click on <b>Create Access Key</b>.  
![Screenshot (1364)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/115052d3-23fc-47c1-8d51-24744562d2ab)  

j) Download the <b>'.csv'</b> after this. (Congratulations ☺️☺️ we are done with the first part of the project).  

A short note on the <id = "section1">Access Key</id>
