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

