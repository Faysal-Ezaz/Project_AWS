Amazon <b>Simple Storage Service</b> / AWS S3 is an <b>object (file)</b> storage service that provides a <b>secure and scalable</b> way to store and access data on the cloud. It is designed for storing data such as <b>files, folders, images, videos, backup and much more.</b>  


Additional Information on S3:  
<ol>
  <li>Buckets must have a <b>globally unique name.</b> </li>  
  <li>S3 is a regional service. </li>  
  <li>Naming convention: No uppercase, No underscore, Between 3-63 characters long, Should always start with a lowercase character or a number.</li>  
</ol>  

<h3>Steps to Create a S3 Bucket:</h3>  
Step_1) First we have to click on “Create bucket”.   


Step_2) The we follow the steps:  
      I)	Under “General Configuration”:   
      img  
      a)	Bucket Name: “test-bucketuser-1” (always lower case or number).   
      img  
      b)	AWS Region: ap-south-1  
      img  
      II)	Nothing Else needs to be changed.  
      img  
      III)	Click on “Create Bucket”.   
      img  
      img  

Step_3) Enter into the bucket by clicking on the bucket name and follow the steps:   
      I)	Under “Objects” ( we will use to upload files).   
      img  
      a)	Click on the Upload button.   
      img  
      b)	Click on ‘add files’.  
      img  
      c)	After uploading the required file(object), click on ‘UPLOAD’.   
      img  
      d)	Then we will click on the close button.  
      img  
      e)	Then we land back on the ‘Upload’ page.   
      img  
      f)	If we click on the file name, we can see more details  
      img  
      g)	Two things, “Object URL” and “S3 URL”  
      img   
      II)	Under “Objects” we will create a new ‘Folder’:   
      img  
      a)	Click on ‘Folder’.  
      img  
      b)	Enter the folder name: “images”  
      img  
      c)	No need to change any other settings.   
      img  
      d)	Click on “Create Folder”.  
      III)	Uploading Files into the Folder:   
      img  
      a)	Under “UPLOAD” page, we click on the newly created folder ‘images’.  
      img  
      b)	Under ‘images’ folder, we click upload.  
      img  
      c)	Then we select the file, we want to upload. (Either a File or a Folder).  
      img  
      d)	Check the Destination and it shows the bucket name/folder name.  
      img  
      e)	Then click on upload. 
      img
      IV)	Deleting the Folder ‘images’ that we created:  
      img  
      a)	Click on the folder, then click on delete.  
      img  
      b)	The folder ‘images’ has been deleted.  
      img
