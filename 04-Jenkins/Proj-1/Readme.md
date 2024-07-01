## Description:  
<ol> 
  <li><b>Objective of the Project:</b>
    <ul>
      <li>Use Jenkins to trigger the build of an EC2 instance.</li>
    </ul>
  </li>
  <li><b>Aim of this Project</b>
    <ul>
      <li>Get acquainted with the Jenkins Interface.</li>
      <li>Learn about Python3's Boto3 <i>(AWS SDK for Python)</i></li>  
      <li>Learn about Putty:
        <ul>
          <li><i>Putty</i> is a free SSH client</li>
          <li>Allows us to connect to Linux EC2 instance from our Computer.</li>
          <li>[Refer to this article to learn more](https://www.earthdata.nasa.gov/s3fs-public/imported/04_Connect_to_an_AWS_EC2_Instance_-_Windows_and_PuTTY.pdf)</li>
        </ul>
      </li>
      <li></li>
    </ul>
  </li>
  <li><b>Software to be used: </b>
    <ul>
      <li>AWS.</li>
      <li>Putty Gen.</li>
      <li>Putty.</li>
      <li>Jenkins.</li>
      <li>GitHub.</li>
    </ul>
  </li>
</ol>  

## Basic Workflow:  
<ol>
  <li>First I will work my way through <b>AWS</b>
    <ul>
      <li>Create EC2 instance
        <ul>
          <li>Get the <b>Key Pair</b> to work with <i>Putty Gen and Putty</i></li>
        </ul>
      </li>
      <li>Create IAM Role </li>
    </ul>
  </li>
  <li>Work with Putty Gen to Generate the .ppk private key.</li>
  <li>Work with Putty to access the EC2 Linux Instance.</li>
  <li>Work with Jenkins to trigger build of an Ec2 instace
    <ul>
      <li>Need to Create a GitHub Repository where the Python Script will be Stored.</li>
      <li>When Jenkins Job is Triggered, the Python script stored in GitHub Repo will build the EC2 instance.
        <ul>
          <li>Need to Connect Jenkins to Github.</li>
          <li>GitHub WebHook to be configured so any changes made to the Python Script in Repo shall trigger the build of a new EC2 instance.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>Lastly, Termination of all the AWS Services Used.</li>
</ol>  

## Final Overview: 
<ol>
  <li>AWS to create EC2 instance.</li>
  <li>AWS IAM to create Role to be assigned to EC2 instance.</li>
  <li>AWS IAM to extract the <b>ACCESS KEYS</b>.</li>
  <li>Putty Gen to extract the private key from .pem file</li>
  <li>Putty to connect to the EC2 instance.</li>
  <li>Jenkins to create Job and trigger build of newer EC2 instances.</li>
  <li>Python3 Boto3 Script that will trigger the build of EC2 instance.</li>
  <li>CleanUp.</li>
</ol>  


# Steps to Create the EC2 instance: 
<ol>
  <li>Step 1: Head to the AWS Console Management >> Search >> EC2.</li>
  <li>Step 2: Under <b>Resources</b>, click on Instances >> <i>Launch Instance</i>.</li>
  <li>Step 3: Then follow the steps => 
    <ul>
      <li>Under <i>Name and Tags</i> assign Name.</li>
      <li>Under <i>Application and OS Images (Amazon Machine Image) </i>, choose <b>Ubuntu</b>.</li>
      <li>Under <i>Instance Type</i>, choose <b>t2.medium</b>.</li>
      <li>Under Key Pair >> Create New Key Pair: 
        <ul>
          <li>Under Key Pair Name >> Enter name of Key Pair</li>
          <li>Under Key Pair Type >> Choose <b>RSA</b></li>
          <li><i>Private Key File Format</i> >> Choose <b>.pem</b></li>
          <li>Click on Create Key Pair.
        </ul>
      </li>
      <li>Under Network Settings >> <b>Edit</b>
        <ul>
          <li>Under <i>Inbound Security Group Rules >> Add Security Group Rule</i>
          <li>Type >> Custom TCP</li>
          <li>Port Range >> 8080 [This is to let allow access to the Jenkins Portal.]</li>
          <li>Also need to add Port 22</li>
        </ul>
      </li>
      <li>For Configure Storage nothing needs to be changed.</li>
    </ul>
  </li>
  <li>Step 4: Then click on Launch Instance to launch the Instance.</li>
</ol>  

# Steps to Create IAM Role. 
<ol>
  <li>Step 1: Head to AWS Console Management >> IAM >> Access Management >> Roles
    <ul>
      <li>Click on Create Role: </li>
      <li>Under Select Trusted Entity
        <ul>
          <li>Trusted Entity Type >> <b>AWS Service</b></li>
          <li>Use Case >> EC2  >> EC2</li>
          <li>Click on Next.</li>
        </ul>
      </li>
      <li>Under <b>Name, Review and Create >> Role Details >> Select Trusted Entities >> Add Permissions >> Add Tags do the following: </b>
        <ul>
          <li>Enter Role Name</li>
          <li>Review the rest</li>
          <li>Click on Create Role.</li>
        </ul>
      </li>
    </ul>
  </li>
</ol>  

# Assigning IAM Role to the EC2 instance: 
<ol>
  <li>Step 1: Head to the AWS Connsole Management >> EC2 >> Instances(Running) then the following steps: 
    <ul>
      <li>Click on the EC2 instance,</li>
      <li>To the Top Right Corner, <b>Actions</b> >> <i>Secruity</i></li>
      <li>Then from the drop down menu, <b><i>Modify IAM Role</i></b></li>
      <li>Then we select the required IAM Role.</li>
    </ul>
  </li>
  <li> Explaination as to why a Role was assigned to the EC2 instance:
    <ul>
      <li>In short, this was done so that, the Python Script can create new EC2 instances without the need for the User's <i>private</i> <b>ACCESS KEYS</b>.</li>
      <li>Providing the <i>Public</i> and <i>Private</i> Access Key is considered risky.</li>
    </ul>
</ol>  

# Working with PuttyGen:  
<b>PuTTYGen</b> is a Key Generator tool for creating SSH keys for PuTTY.  
The basic function is to create <b>public</b> and <b>private</b> key pairs.  
Before Working with PuTTYGen, it is suggested to create a separate folder to store the <i>.pem</i> and <i>.ppk</i> files.
<ol>
  <li>Open PuTTYGen >> Actions >> Load an Existing Private Key File <b>Load</b>.
    <ul>
      <li>Load Private Key Dialogue box Opens up</li>
      <li>From the Dropdown menu, click on <b>All Files</b> >> select the <i>.pem</i> file</li>
      <li>Cick on Open</li>
      <li>It shows "<b>You have sucessfully imported the file format</b>", click on OK</li>
    </ul>
  </li>
</ol>   

# Working with PuTTY:  
<b>It allows to connect to remote computers or devices using various protocols such as secure socket shell (SSH), Telnet, login, and more.</b>
<ol>
  <li></li>
</ol>
