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

Here we will be borrowing some of our code from the following website: (https://registry.terraform.io/providers/hashicorp/aws/latest/docs).  Again this website doesnot belong to me and is only for reference purpose.



Tools Required for this mini Automation Project: 
  a) Gitbash.
  b) AWS Console.

The general workflow will be as follows: 
Firstly, we will create an IAM user, assign it the "AdministratorAccess" Role and finally create an "Access Key". More on Access Key later on in this project and why it is actually used. 
Secondly, we will open GitBash and type in some command, 
