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




<details>
  <summary>Please ignore this, this is only for my refernce. </summary>
  Refer to this link for Terraform Cheat sheet.  
  https://spacelift.io/blog/terraform-commands-cheat-sheet
</details>
