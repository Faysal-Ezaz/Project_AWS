# Automating the <b>creation</b> of AWS EC2 instances using Terraform: 
<details>
<summary><strong>Table of Contents</strong></summary>
  <ul>
    <li>
      <a href="#about-the-project">About the Project</a>
    </li>
    <li>
      <a href="#software-and-platforms-used">Software and Platforms used</a> 
      <ul>
        <li>GitBash</li>
        <li>Amazon AWS</li>
        <li>Terraform</li>
      </ul>
    </li>
    <li><a href="#explaination-about-the-softwares">Explaination about the softwares</a>
      <ul>
        <li>About Git</li>
        <li>About AWS</li>
        <li>About terraform</li>
      </ul>
    </li>
    <li><a href="#commands-used">Commands Used</a></li>
    <li><a href="#hands-on">Hands On</a></li>
  </ul>
</details> 

<!-- About the project -->
## About the Project 
Here I shall be using <b>Terraform</b> [HCL](https://www.shecodes.io/athena/2110-what-is-hcl-infrastructure-automation-language#:~:text=HCL%20(HashiCorp%20Configuration%20Language)%20is,%2C%20integers%2C%20strings%20and%20more.)(HashiCorp Configuration Language) that's designed for infrastructure automation.  
It has a syntax similar to JSON and supports Boolean, Integers, Strings, and more.   
Using Terraform HCL language, I will automate the <b>creation</b> and <b>deletion</b> of EC2 instances.  
Moreover, The code specific code snippets will also be added.   
Links to the code snippets on Terraform website shall also be added.   
Other than that, <b>Amazon AWS</b> shall be used as EC2 instances shall be automated.  
Lastly, Git software shall be used as the Command Line to write all the codes.   

## Software and Platforms used  
[GitBash](https://git-scm.com/downloads) Click on this to Install GitBash CLI!  
[Amazon Web Services](https://aws.amazon.com/free/?gclid=Cj0KCQiA5fetBhC9ARIsAP1UMgESWbcWaBqkpQLyXzAFMOau-lEZmO0XAVO5W7_XWl96v4wMG-f8r0waAvMmEALw_wcB&trk=09863622-0e2a-4080-9bba-12d378e294ba&sc_channel=ps&ef_id=Cj0KCQiA5fetBhC9ARIsAP1UMgESWbcWaBqkpQLyXzAFMOau-lEZmO0XAVO5W7_XWl96v4wMG-f8r0waAvMmEALw_wcB:G:s&s_kwcid=AL!4422!3!453325184878!e!!g!!aws%20amazon%20console!10712784862!111477280451) Create a New AWS Account    
[TerraForm](https://www.terraform.io/)  IaC Tool to be used for this project. 

## Explaination about the softwares  
1. <b>GitBash</b>:
   Git Bash is an application for Microsoft Windows environments which provides an emulation layer for a Git command line experience.
2. <b>AWS</b>:
   Amazon Web Services (AWS) is the world’s most comprehensive and broadly adopted cloud, offering over 200 fully featured services from data centers globally.
3. <b>Terraform</b>:
   Terraform is an Infrastructure As Code Tool that lets us build, change, and version cloud and on-premise resources safely and efficiently.

## Commands Used  
<b> First we will need to create a folder to store and work on the terraform files and directories.  
For this we will do the following:  
We need to go to the Directory where we will be storing and executing the file creation. I prefer <b>'D'</b> drive for this task.  
Then, we will create a new folder and name it Terraform.  
Then, we do the following: ![Screenshot 2024-02-04 033206](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/901403dc-472c-4ea0-bdfe-6470881d3b46)  
From the dropdown menu, we click on <b>Open GitBash here.</b>  
#### For the <b>Commands</b>  
<b>Git Bash commands: </b>  
1. `pwd` This will verify if we are in the correct directory and the correct file.  
2. `vi file1.tf`  This will create the new terraform file.  

<b>Terraform Commands</b>  
1. `terraform init` to prepare the working directory for use with Terraform, this command performs Backend Initialization, Child Module Installation, and Plugin Installation 
2. `terraform validate`  Validate the configuration files in your directory and does not access any remote state or services.
3. `terraform plan`  Plan will generate an execution plan, showing you what actions will be taken without actually performing the planned actions.
4. `terraform apply`  Create or update infrastructure depending on the configuration files. By default, a plan will be generated first and will need to be approved before it is applied.
5. `terraform destroy`   Destroy the infrastructure managed by Terraform.

### Hands-on Action Plan: 
<ol>
  <li>Firstly, we will log into AWS Console Management and create an IAM user.</li>
  <li>Then we go back to GitBash and create a new file named `file1.tf`</li>
  <li>We then create a new EC2 instance. Also, the AMI id too is required for later use.</li>
  <li>We go back to GitBash CLI, copy some code snippets from Terrafom.io and past it in the window</li>
  <li>We shall then use the terraform commands in the relevant order.</li>
  <li>At last we have to use the command <i>terraform destroy</i> to remove all the infrastructure managed by AWS.</li>
</ol>  

## Hands On:   
Assuming that the above steps(Creating a new <b>terraform directory</b> on system, <b>installing terraform</b> and <b>gitbash</b> is done, also <b>signed in to AWS</b> Account) are done, we shall proceed with the following steps:  

<b>GitBash</b> codes:  
- `pwd`: This will help verify the current directory.
- `vi terrfile1.tf`: This will take us to another input screen <b>(Let for out reference, call it <i>vi</i> editor), Inside that screen, we need to type in the following code:
```terraform
terraform {
 required_providers {
   aws = {
     source  = "hashicorp/aws"
     version = "~> 5.0"
   }
 }
}
```
The result of the code shall be that, it will help us connect to the <b>AWS Server</b>.   
In order to exit this <i>vi text editor</i>, first press `ESC` followed by `:wq`  
In the <b>Git Bash</b> console, typing `~ls -a`, the result should be `terrfile1.tf`.

After this is done, we will need to work with some <b>terraform code</b>.   
In the GitBash console, we type the command  
```terraform
terraform init
```
If everything is done correctly, the result should be `All the plugins are initialized in the backend`  

After the `terraform init` command is initialized, we will move to our <b>AWS Account</b>.  
<ol>
  <li>
    First we move to <b>AWS IAM</b> and create a User by following the steps:
    <ul>
      <li>Under 'User details': fill up name, and click on next.</li>
      <li>Under <b>Permission Options</b>, click on <i>Attach Policies directly</i> and then click on 'Administrative Access'.</li>
      <li>Under Review and Create, click on <b>Create User</b>.</li>
    </ul>
  </li>
  <li>
    Next, we click on the <b>Created User</b> and try and generate the <i>Access Key</i>
    <ul>
      <li>Click on `Create Access Key`</li>
      <li>Then `Application Running on an AWS Compute Service. `</li>
      <li>Then `Click on Create Access Key. Download the .CSV file`</li>
    </ul>
  </li>
</ol>  
The outcome of the above task shall be the <b>Creation of a Terraform User</b>, give <b>Admin Access</b> to the user by setting up the <i>permissions</i>.  
After this there shall be no need to Visit AWS Console again.  

#### Coming back to Git Bash again:  
we open the file by typing `vi terrfile1.ts` this redirects us to the vi editor.  
```terraform
provider "aws" {
  region     = "ap-south-1"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
} 
```
Then we exit the vi editor using the commands `ESC` followed by `:wq`.  
After the above code is written in the Vi editor,   
In GitBash console, we type the command:   
```terraform
terraform plan
```
but at this phase it will show no changes. As we havent created any instances yet.  
```terraform
terraform apply
```
even this shall show no changes that are to be made.   
`Apply complete! Resources: 0 added, 0 changed, 0 destroyed.` This is the output for the <b>Apply</b> code.  

Now, we go the `file1.tf` and write the <b>code for EC2 instance creation</b>.   
For this we type `vi file1.tf` in <b>GitBash</b> console. Following this the vi file editor should open up,  
Now to copy the code snippet, we redirect to [Click on this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance).  
AWS Provider > EC2 ( Elastic Compute Cloud ) > aws_instance.   then we copy the following and paste it in vi file editor.  
```terraform
resource "aws_instance" "web" {
  ami           = "provide_your_ami_id"
  instance_type = "t2.micro"

  tags = {
    Name = "server1"
  }
}
```  
here, we are creating the <b>EC2 isntance</b>, <i>web</i> is the name of the instance, (we can change the name if needed).  
[To fetch AMI id](https://www.youtube.com/watch?v=BkG09nrh_7s), always remember to put the ami id in double quotes.  
Next, we exit the vi file editor console by pressing `ESC` button followed by `:wq`.  

Next in the GitBash console, we execute the following commands.  
In order to dry run/check for any syntax errors, we type the command  
```terraform
terraform validate
```
this shows any possible error that may be present.   
if there are no errors in the code then, `Success! The configuration is valid` shall be shown.  


<details>
  <summary>Please ignore this, this is only for my reference. </summary>
  Refer to this link for Terraform Cheat sheet.  
  https://spacelift.io/blog/terraform-commands-cheat-sheet  

Now, we have to redirect to AWS console:  
Inside, we open EC2 Console, click on <b>instances</b>.  
Then click on <b>Launch instance</b>.  
We select the <b>appropriate AMI</b>.  

</details>
