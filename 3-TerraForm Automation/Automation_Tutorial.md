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
Firstly, we will create an IAM user, assign it the "AdministratorAccess" Role and finally create an "Access Key". More on Access Key later on in this project and why it is actually used. 
Secondly, we will open GitBash and type in some command, 



Here we will be borrowing some of our code from the following website: (https://registry.terraform.io/providers/hashicorp/aws/latest/docs).  Again this website doesnot belong to me and is only for reference purpose.
