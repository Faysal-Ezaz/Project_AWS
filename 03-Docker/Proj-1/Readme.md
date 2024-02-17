# Learning about the main Docker commands to create and delete and manage the docker containers:  
For this we will need to focus on these core points:  
<details>
  <summary>Click to expand</summary>
<ul>
  <li><a href="#AWS">AWS</a></li>
  <li><a href="#Putty-Gen">Putty Gen</a></li>
  <li><a href="#Putty">Putty</a></li>  
  <li><a href="#Docker-Commands">Docker Commands</a></li>  
  <li><a href="#Work-Plan">Work Plan</a></li>
</ul>
</details>  

## AWS  
For this part, I will be focusing on <b>creating an AWS EC2 instance</b>, <b>creating a new Key pair</b>, <i>acquiring</i> the <b>Public IP address</b> of the newly created EC2 instance.  


## Putty Gen  
For this, I will need to install the software <b>[Putty](https://putty.org/)</b> and open <i>Putty Gen</i>.    
Then need to follow the steps:  (main overview is that using this software we convert the `.pem` file to `.ppk` file)  


## Putty  
For this I need to use the <b>Putty software</b>  
Using this software we will connect to the main terminal where all the docker commands will be written.  


## Docker Commands  
These commands are essential as they will help, create the container, for this there are a few steps that needs to be executed in order to achieve the same.  
They are as follows:  
<ul>
    <li>
      To create the containers: 
      <ol>
          <li>We need to call the images first.</li>
          <li>After this we will be able to create the docker containers.</li>      
      </ol>
    </li>
    <li>
      To delete the containers: 
      <ol>
        <li>All the containers created have to be deleted</li>
        <li>Then the images can be removed and the vice versa is not possible</li>
      </ol>
    </li>
</ul>    


## Work Plan:  
### First we have to work with AWS:  
<ol>
  <li>
    Create an EC2 instance.  
      While creating the EC2 instance, there is a small step that needs to be performed:   
      <ul>
        <li>First we head over to <b>Security group</b>, Enter the name for the <i>security group</i></li>
        <li>Then we install the `.pem` file in our system.</li>  
      </ul>
  </li>
  <li>After creation of the EC2 instance, we need to copy the <b>Public IPv4</b> of the same.</li>  
</ol>  
### Then coming to Putty Gen software,  
<ol>
  <li>First we open Putty-Gen</li>
  <li>Then we click on Load and head over to the location where the `.pem` file is stored.</li>  
  <!--I will add all the steps later on after this.-->
</ol>
### Then working with <b>Putty Software</b>  
  <!--I shall add this in this later on moving on to the Docker commands.-->   


### Docker Commands required:  
`Sudo su` This command is used to become the root user.  
`yum update -y`  Update Command Center.  
`yum install docker` To install Docker.  
`service status docker` Command to check if Docker is Installed or not.  
    - `service docker start` Command to start Docker.  
    - `service docker status` To recheck.  
`docker info` To get information of the system where Docker is Installed.  
`docker images` To check the <i>number of docker images</i> built.  
`docker ps` To see only the running containers  
    - `docker ps -a` This is to check all the containers.  
`docker run ubuntu` check and pull(install) the image create and continue.  
    - `docker ps -a`  
    - `docker images` These two commands are used to check again.  
`docker run --name(abc) ubuntu/bin/bash`  Command to run the container.  
``
