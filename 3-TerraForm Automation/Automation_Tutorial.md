<b>This is a project where I shall be using <b>Terraform</b> to Automate the creation of an EC2 instance/instances.<b>  
Pre-requisits:  
(a) <b>AWS IAM</b> and  
(b) <b>AWS EC2</b>. Please keep in mind that this will contain a detailed explaination of all the commands used and all the steps followed.  

A <i>short note</i> on <b>Terraform</b> and why it is used:  
Terraform is an <b>infrastructure as code</b> tool that lets you <i>build, change, and version</i> cloud and on-prem resources safely and efficiently.  
Terraform was first released in July 2014 by a company named <b>"HashiCorp"</b>.  
Terraform creates and manages resources on cloud platforms and other services through their application programming interfaces (APIs). Providers enable Terraform to work with virtually any platform or service with an accessible API.


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
Firstly, we will create an IAM user, assign it the "AdministratorAccess" Role and finally create an "Access Key". More on <a href = "#section1">Access Key</a> later on in this project and why it is actually used/needed. 
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

<strong>Step-1: Working with AWS IAM service.</strong> (we open aws console and type IAM on the search bar) 
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

A short note on the <a id = "section1">Access Key</a>:  
<ul>
  <li>Access keys are long-term credentials for an IAM user or the AWS account root user</li>  
  <li>We can use access keys to sign programmatic requests to the AWS CLI or AWS API (directly or using the AWS SDK).</li>  
</ul>  

Now enter the description for EC2 instance "AMI key".  

<strong>Step-2: Working with EC2 instance.</strong> (We will type EC2 in the Search box).  
a) Under Instances, click on <b>Launch Instances</b>
  ![Screenshot (1365)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/7b79358b-b461-4ee0-93e6-4da0409ad647)  
  
b) Under <i>Names and Tags</i>, enter any name
![Screenshot (1366)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/dd109ba0-493e-429b-9c26-f74fd82a6b7d)  

c) From Amazon Machine Image Section, we copy the <b>"AMI ID"</b> and store it on a notepad for later use. 
![Screenshot (1367)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/18c137c0-7435-4af1-afd6-3f55fee39f94)  

The <b>Main Purpose</b> for using the <i>AWS EC2 service</i> was to fetch the <b>AMI ID</b> and nothing more.  

Now we will be working with <b>Terraform Commands</b> to automate the entire process, for this we have to open <b>GitBash</b> and enter the following commands.  

Step 3: Open <b>GitBash</b> and do the following steps:  (Please keep in mind that for me by default the gitbash opens in C Drive, so i will do it accordingly).  
a) <b>cd</b> documents   (This is used to change the directory to <b>documents</b>)
b) <b>mkdir</b> terraformFolder   (This is used to create a new folder named <b>terraform</b>)  
c) <b>cd</b> terraformFolder   (This is used to change the folder to <b>terraform</b>.)
d) <b>mkdir</b> GitUploadProject   (This is used to create a new folder named <b>GitUploadProject</b>)  
e) <b>cd</b> GitUploadFolder   (This is used to change the folder to <b>GitUploadProject</b>)
f) <b>vi</b> file1.<b>tf</b>   (This is a <b>terraform</b> command to create a <b>new terraform file</b>)  

![Screenshot (1369)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/a6aef5d6-a6f9-4596-9aa5-ea59f601f8b8)  
Your GitBash should look something like this.  

Now we will have to take reference code from the <strong>terraform website</strong>.  
(https://registry.terraform.io/providers/hashicorp/aws/latest/docs) This is the official website from which we shall be borrowing the code snippets.  

<h2>Important</h2>  

Now the steps to be followed are:  
Whenever we type in the command, <b>{vi file1.tf}</b>, inside the GitBash console, another screen appears.  
Inside that console, First we will have to press the <b>Insert</b> keyboard button, for us to be able to write any code on the console.  
![Screenshot (1370)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/96a4e0bc-5628-4f88-a061-1e0e806a0f9b)  
The console looks like this.  

Now we come back to the coding part:  (Keep in mind that all of the code will be TerraForm Code)

Step-4: We head over to the Terraform website and copy the following highlighted code snippet.  
![Screenshot (1371)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/566d5e08-0060-4729-a5ec-bf98d5dd5904)  

a) We then paste it in the GitBash Console <b>(refer to the below screenshot before proceeding with this step)</b>  
![Screenshot (1372)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/eb92f000-3c94-4806-b8d9-f1a085b5f74e)  
It should look like this.  

b) Now there is another important step to be followed to exit the input console. <b>Press the <b>ESC</b> Keyboard button</b> then type in <i>:wq</i> and press enter, it should look something like this.  
![Screenshot (1372)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/4504e640-0b2a-4a83-9981-d44243c56c33)

c) Then in the original GitBash console, type the command <b>terraform init</b> (refer to the below screenshot)!! 
![Screenshot (1375)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/776fd244-a5d7-4f88-b451-5a0f90740407)  

d) We will again type the command <b>vi file1.tf</b>, following this the GitBash input console will appear again, there we will paste the following code( Please refer to step{e} for code fetching.  
![Screenshot (1378)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/ae2ff9a2-e3e8-4e35-aecd-96d0568f8ab4)

e) For this, we will have to scroll down to <b>"Provider Configuration"</b> and then copy the code from <i>Usage:</i>
![Screenshot (1377)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/75368ec6-f0a2-47d5-85dd-cd117b7f2eb4)  

<b>Important</b>
Please keep in mind that <b>one change</b> has been made to the code, that is (<b>region = "us-west-2"<b> has been changed to <i>region = "ap-south-1"</i>). This is region specific and can be changed accorddingly.  
Now we previously saved the <b>Access Key</b> ".csv" file, we need to open that and paste that in their respective places.  
<b>access_key = "AKIARLWOAA5XCJNJ74EU" </b>  
<b>secret_key = "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" </b>  
Keep in mind that you have to make changes accordingly, the above <i>access_key</i> and <i>secret_key</i> are copied from my <b>.csv file</b>.  

f) In order to exit the GitBash Input console we again press the <b>ESC</b> keyboard key and type the command "<i>:wq</i>". This will send us back to the original GitBash Console.  

g) Then we type in the command <b>terraform validate</b>.   
![Screenshot (1378)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/40b7502a-0c19-40cd-bdd9-8ecde2b269f4)  

h) We again return to the GutBash input console by typing the command "<b>vi file1.tf</b>".  

i) Next we head back to the Terraform Website and there under "<i>aws provider</i>" we have to find "<i>EC2(Elastic Compute Cloud)</i>".  
![Screenshot (1376)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/18d72230-5077-4f25-804a-6eff7993b94e)  

j) We will have to copy a section of the code, for this under "Resources", we scroll down to "<b>aws_instance</b>"  
![Screenshot (1380)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/0ca90cfc-ce63-4220-8ab7-59c7512f8ee0)  

k) Then we copy the following code:  
![Screenshot (1381)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/f1fd9121-884a-4330-859c-d55f0ee7a46c)  

l) We past the code in the GitBash Input console: (also keep in mind that we have made a few changes, refer to the below screenshot for proper reference, especially the ami-id <b><i>REFER to step-2 part(c)</i></b> for this!)  
![Screenshot (1382)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/a56e80cb-db45-40ca-b1b2-5f50c67f6b51)  

m) We then press the "<b>ESC</b> button and then type the command "<i>:wq</i>", this will return us to the original GitBash console.  
![Screenshot (1383)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/93a51dec-231d-4997-aafa-c753c3b4d4ac)  

Step-5: From this step onwards, we will see how the EC2 instance is automatically created 
a) In the GitBash console, type the command "<b>terraform validate</b>. This will check for any potential errors.  
![Screenshot (1384)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/e1fa5dba-ba15-4330-8592-e2fa6967b4f8)  

b) Then we type the command "<b>terraform plan</b>".  
![Screenshot (1386)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/a18e48b8-3c20-430d-a739-9f4e8d875654)  
![Screenshot (1387)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/f2a7010f-31ac-448e-8a12-da5aac1b6cf0)  

c) Then we type in the command "<b>terraform apply</b>"  
![Screenshot (1388)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/ab05dee9-18b9-41b8-a163-8bf155242c2e)  
after this type in "yes" (refer to the below screenshot)  
![Screenshot (1389)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/7870cd23-df28-434a-a3e6-c289509c54de)    

d) After we typed 'yes', we have to go back to AWS console and open up EC2, there we will see that our instance, <b>Server1</b> has been created and is running.  
![Screenshot (1346)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/93a6e679-08c9-4d9b-9be5-652d148898b0)  

e) Now that the EC2 instance "<b>Server1</b> has been created, we need to terminated the instance, for this open <i>GitBash</i> terminal, and type the command, (<b>terraform destroy</b>). 
![Screenshot (1347)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/93da59e7-52c9-4ef2-b132-9b12d597ef1c)  

Remember to type <b>"yes"</b>
![Screenshot (1348)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/3c3faf97-27d3-4ee3-a5dc-56bc1e109908) 
![Screenshot (1349)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/f0455cd4-8c95-4cea-b37e-43a066fa9628) 



Now, the above command will terminate our Instance "Server1". 

Congratulations, the entire project is complete ☺️☺️..  
Hope you enjoyed this project.  
Make sure to drop a follow for more such projects.  
Thank you bye 👋. 


