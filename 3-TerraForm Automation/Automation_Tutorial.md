This is a project where I shall be using <b>Terraform</b> to Automate the creation of an EC2 instance/instances. 
Pre-requisits: (a) <b>AWS IAM</b> and (b) <b>AWS EC2</b>. Please keep in mind that this will contain a detailed explaination of all the commands used and all the steps followed. 

  
<u>Software Requirements:</u> 
Head over to this website to install Terraform (https://developer.hashicorp.com/terraform/downloads)
Then install the following 
![Screenshot (1352)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/c014ecc1-d2bf-4dd3-b0c0-0c45fc2c9766)
Then we will head over to 'C' drive of our system and inside 'C' drive we open "Program Files".
Inside 'Program Files', we will create a folder "terraform" and then unzip the previously downloaded software (terraform software).
Next comes the part where we add the path for the software in system variables. For this we have to follow the 

Here we will be borrowing some of our code from the following website: (https://registry.terraform.io/providers/hashicorp/aws/latest/docs).  Again this website doesnot belong to me and is only for reference purpose.



Tools Required for this mini Automation Project: 
  a) Gitbash.
  b) AWS Console.

The general workflow will be as follows: 
Firstly, we will create an IAM user, assign it the "AdministratorAccess" Role and finally create an "Access Key". More on Access Key later on in this project and why it is actually used. 
Secondly, we will open GitBash and type in some command, 
