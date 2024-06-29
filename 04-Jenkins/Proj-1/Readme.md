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
</ol>
