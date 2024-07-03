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
  <li>Open PuTTY Configurations
    <ul>For Host Name, the name has to be of the form [default_name]@Ip eg: ec2-user@IP
      <li>First we copy the name for the EC2 instance which can be done by Instances >> Connect >> copy the name assigned there.</li>
      <li>Copy the Public IP</li>
      <li>Under Host name, fill the name.</li>
    </ul>
  </li>
  <li>From Category:
    <ul>
      <li>Connection >> SSH </li>
      <li> Auth >> Credentials</li>
      <li>Under <i>Private Key File for Authentication:</i> >> Browse</li>
      <li>Click on Ok</li>
      <li>Under Basic Options for your PuTTY session, click on <b>Save</b></li> 
      <li>Finally click on Open</li>
    </ul>
  </li>
</ol>    

## Important point to note:  
At this point we have to understand that, The PuTTY console is a <b>remote console</b> that connects to the EC2 instance whose Public IPv4 was verified at the PuTTY Console.  
So any command and any changes triggered in the PuTTY remote console will directly effect the EC2 instance. 

# Working with the PuTTY SSH terminal:  
<ol>
  <li>First install Java</li>
  <li>Then install Jenkins</li>
  <li>Then install Git</li>
  <li>Then install Pip3</li>
  <li>Then install Boto3</li>
</ol>    
  
## Follow along the steps to do the same:  

1) `sudo su`  This command will grant us the <b>admin access</b>.
2) `sudo apt update`  This command refreshes the list of available packages and their versions.
3) `sudo apt upgrade`  This command downloads new packages to a user's distribution.
4) `sudo apt install openjdk-11-jdk`  This will install Java JDK onto our EC2 instance server. Jenkins needs Java to operate hence we install Java first.
5) `java --version`  If the output of this command is a version number then we can be rest assured that Java has been successfully installed.
6) `wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add - 
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`  This is the Jenkins Repository that we need <b>for easier Installation and Updates</b>.
7) `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5BA31D57EF5975CA` This is the <b>GPG key</b>.  GPG-based signing workflow improves software security and seamlessly integrates with DevOps processes to sign binaries on Windows and Linux.
8) `sudo apt update`
9) `sudo apt install jenkins`  This command will install the latest version of Jenkins onto out EC2 instance.
10) `sudo systemctl start jenkins`  This will start the Jenkins session onto our EC2 instance Server.
11) `sudo systemctl enable jenkins`  This is to enable the Jenkins service to start on the system boot.
12) `sudo apt-get install python3-pip3` This command shall allow us to install pip3 onto our EC2 server.
13) `sudo apt install git-all`  This command shall allow us to install GIT onto the EC2 server.
14) [To install Boto3 refer to this article](https://stackoverflow.com/questions/54753301/how-to-install-boto3-on-ubuntu-18-04).

Now that <b>Jenkins</b> and all other necessary software are installed onto out EC2 instance server,  
We need to access the Jenkins Server where we will be creating <b>Jenkins Jobs</b>.  

For this we need the <b>Public IPv4</b> of the EC2 instance.  
` http://your-instance-ip:8080`  Keep in mind that `your-instance-ip` should be replaced by the IP address of the EC2 instance.  

Now The Jenkins Server will prompt for the <b>Admin Password</b>.  
`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`  This command on the <b>PuTTY remote Server</b> will give us the Password. Copy and Paste to <i>Unlock jenkins</i>.  

## Working with Jenkins:  
<ol>
  <li>Getting Started
    <ul>
      <li>Click on Install Suggested Plugins.</li>
    </ul>
  </li>
  <li>Create Admin User
    <ul>
      <li>Donot click on <b>Skip and Continue as Admin</b>.</li>
      <li>Enter Username</li>
      <li>Enter Password</li>
      <li>Confirm the Password</li>
      <li>Enter Full Name</li>
      <li>Click on Save and Continue.</li>
    </ul>
  </li>
</ol>  
Now the Jenkins Setup is Ready!   

## Now main Jenkins Part:  
The main purpose of Jenkins is to create a <b>Job</b> which when triggered will build an EC2 instance for us. 


