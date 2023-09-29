Hello Everyone 👋 this is a guide on how to <b>Create a basic EC2 instance</b> and use <b>EC2 User Data Script</b>.  

Now, before using the <i>EC2 User Data</i> let's dive deep into what is <b>EC2 User Data</b> and what is the need of using an EC2 User Data Script:  
a) By using the <b>EC2 User Data Script</b>, we can <i>Bootstrap</i> our EC2 instances.  
b) Bootstrapping means <b>"Launching Commands"<b> when a machine starts.  
This <i>script</i> is run <b>only once</b>, when the machine first starts!  
EC2 User Data is used to automate tasks like:  
i) Installing Updates.  
ii) Installing Software.  
iii) Downloading common files from the Internet, and so on.  
A point to be noted is that the EC2 User Data Script runs with the <b>'Root User'</b>.  
To know more about the EC2 User Data and BootStraps refer to this website : (https://blog.devops.dev/aws-ec2-elastic-compute-cloud-8f964f844461).  
Friendly reminder " I am not the owner of the content in the 'medium website' and I am pasting the link just for reference purpose. "

<h2>Now, We will look into the steps on how to <b>create</b> an EC2 instance and how to host the Website!</h2> 

<b>Step 1:</b> Login to AWS Console. 

<b>Step 2:</b> In to AWS console head to <i>Search</i> and type <b>'EC2'</b>. and the results should appear as follows: 
![Screenshot (1267)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/fd23901f-b7a5-4fc4-9093-51f41e4b8059)
Now we are greeted by the EC2 console window, which appear somewhat the following picture depicts (Since Amazon has taken the initiative to change the appearance of how AWS looks, with time the appearance may change!).
![Screenshot (1268)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/2440fcdd-9fc5-4af8-bdca-2e08ea4f3f09)  

<b>Step 3:</b> Under <i>'Resources'</i>, click on <b>"Instances"</b>.  
  a) The <b>'Instances'</b> window shall open up.  
  b) Now make sure to click on "Launch Instances".  
![Screenshot (1269)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/b604413a-787f-4736-a7fc-8b4272ef9f92)

<b>Step 4:</b> <b>Launch an Instance</b> Tab opens up, now we follow the steps:  

  a) Under 'Name and Tags', we enter the 'Name' here the name will be "My First Instance".  
  ![Screenshot (1257)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/3b3277d8-f916-4399-a62b-37430a762d6d)  
  
  b) Under 'Application and OS Images (Amazon Machine Image)', we choose "Amazon Linux" and for 'Amazon Machine Image(AMI), we choose "Amazon Linux 2 AMI (HVM)" and we make sure that it is Free Tier Eligible.  
  ![Screenshot (1258)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/182552c1-98c9-4383-878e-291827767b83)  
  
  c) Under Instances Type, we choose "t2.micro" which again is Free Tier Eligible. ( Instance type determines the no of cores, memory capacity, etc.
  ![Screenshot (1259)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/476817aa-5733-437e-856c-78dc78c757e3)
    
  d) For Key Pair Login, we click on "Create new Key Pair" and the following window shows up.  
    i) Here we enter the name as "EC2 Tutorial".  
    ii) For 'Key Pair type', we select "RSA".  
    iii) For 'Private File Key Format", we select ".pem"(For Windows 10 and higher, linux and MAC) or ".ppk" for (Windows 8 or lower)  
    iv) Then we click on 'Create Key Pair'.  
    ![Screenshot (1271)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/7e760256-1376-49ca-85e0-988c214b32f4)
  
  e) Under 'Network Settings', we leave most of the things untouched and only change a few settings:  
    i) Enable Allow HTTPS traffic from the Internet.  
    ii) Enable Allow HTTP traffic from the Internet.  
    ![Screenshot (1272)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/e15629df-e683-4cf1-94b5-8b91f4e3d951)
  
  f) Under Storage(Volumes), we need to change one setting:  
    i) Firstly we have to click on 'Advanced'.  
    ii) Then we click on 'Show Details'.  
    iii) Then we turn on 'Delete on Termination'.
    ![Screenshot (1262)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/60f6a05c-a119-4a49-b23f-c00bd7546544)
  
  g) Under Advanced details, we have to set the EC2 User Data Script, bootstrap.  
    i) Firstly click on the arrow next to Advanced details, so we get more options.  
    ii) Then we scroll down to 'User Data'.  
    iii) Then we enter the following code (Please copy the code from the attached screenshot!). 
    ![Screenshot (1263)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/c1237bfa-02b2-4b64-8774-605b13431bc1)
  
  h) Under Summary check all the information provided.  
    i) We only keep <b>'1'</b> instance.  
    ii) Then we click on <i>'Launch Instance'</i>. 
    ![Screenshot (1264)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/f1726038-b1fe-44a8-9422-fdb4cad9691a) 

<b>Step 5:</b> We wait for the <b>2/2</b> under <i>'Status Check'</i>.
![Screenshot (1266)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/d5d8ed87-d541-4d48-92ac-32e110088af3)
  
<b>Step 6:</b> Lastly, we copy the public IPv4 address and paste it on a new tab.  
