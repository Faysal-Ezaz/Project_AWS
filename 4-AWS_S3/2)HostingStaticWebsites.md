Amazon S3 can be used to host static websites:   

Please keep in mind that the steps mention below are the steps to host a website without updating the S3 bucket policy.  
The steps to host a static website by updating the S3 bucket policy have been mentioned in this readmefile (https://github.com/Faysal-Ezaz/Project_AWS/blob/main/4-AWS_S3/S3_Security(Bucket-Policy)-handsOn.md) 

Steps to host:  

At present we have two files in the bucket:  
![Screenshot (1585)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/c7abdfe0-e7f0-4254-a4e4-03f32010ce3a)

Step_1) Click on <b>Properties</b>, scroll all the way down and we will find "Static Website Hosting", and follow the steps:  
![Screenshot (1586)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/702cca8d-0836-4bd2-9c51-2ab405d43630)
   I) Click on Edit,  a new screen appears. 
   ![Screenshot (1588)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/25a4d5a6-1f3c-4fe5-83ed-b1d5e107de4b)  
   II) Make the following changes and click on "Save".  
   ![Screenshot (1589)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/89e9a05f-fa9c-4f14-8761-7f7abe443f0d)  

 Step_2) We go back to "OBJECTS" and click on 'Upload'.  
   I) We upload another index.html file.  

 Step_3) We go back to Properties, scroll all the way to "Static Website Hosting", copy the link and paste it. 
![Screenshot (1590)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/2dc0afb3-7b0d-4c35-8c58-6e2f677e0df5)

<b>Now, refer to Article No.3 for reference on how to set the bucket poilcy</b>  
There i have mention all the steps and elaborated on them. So, there shall be no issue while hosting a static website with an S3 policy.  
