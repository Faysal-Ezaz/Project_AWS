First we head over to Buckets under S3, then we open the bucket named <b>test-userbucket-1</b> and then follow the following steps:  

Step_1) We head over to <b>Permissions</b> and follow the steps:   
      I) Under "Block Public Access",  we have to click on <b>Edit</b>   
      ![Screenshot (1582)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/f03f2bc0-20de-426e-bcc4-0df8e6f79654)
      II) We have to press on <b>"Block <i>all</i> public access"</b>.    
      ![Screenshot (1583)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/92a93499-dacf-4f0e-b595-33dba760edef)  
      

Step_2)  
      I) Under <b>Bucket Policy</b>, we will click on <b>Edit</b>.  
      ![Screenshot (1574)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/6cadfc12-cbfe-420d-ac05-6790cb5e5fbb)  
      II) We then click on <b>Policy Generator</b>.  A new tab shall open up.  
      ![Screenshot (1575)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/c5f9a214-012f-439f-a6a5-4e375ae0afb7)  
      

Step_3) Under <b>AWS Policy Generator</b>  
      I) Select Type of Policy: " S3 Bucket Policy".  
      II) Principal: "*" (Simply because we want to allow anyone to be able to access it).  
      III) Actions: GetObject.  (applied to objects within our bucket).    
      ![Screenshot (1578)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/bf52fd61-eada-430c-be1e-35789267886f)  
      IV) Amazon Resource Name (ARN) copy it from Edit Bucket Policy and then paste it followed by a "/" and "*".  
      ![Screenshot (1579)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/13e1875e-3c0b-427c-a8d5-b0beff2764eb)  
      V) Then we will click on <b>Add Statement</b>.  
      VI) Then we will click on <b>Generate Policy</b>.    
      ![Screenshot (1580)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/56237105-6d5c-4db9-869c-1ad322c6b3ab)  
      VII) Then we will <i>copy</i> the code.  
      VIII) Then we head back to the previous tab and then <b>paste the code</b> under "Policy".  
      IX) Then we click on <b>Save Changes</b>
![Uploading Screenshot (1584).png…]()
