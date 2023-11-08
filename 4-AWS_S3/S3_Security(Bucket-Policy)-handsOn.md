First we head over to Buckets under S3, then we open the bucket named <b>test-userbucket-1</b> and then follow the following steps:  

Step_1) We head over to <b>Permissions</b> and follow the steps:  
      I) Under <b>Bucket Policy</b>, we will click on <b>Edit</b>.  
      II) We then click on <b>Policy Generator</b>.  A new tab shall open up.  

Step_2) Under <b>AWS Policy Generator</b>  
      I) Select Type of Policy: " S3 Bucket Policy".  
      II) Principal: "*" (Simply because we want to allow anyone to be able to access it).  
      III) Actions: GetObject.  (applied to objects within our bucket).  
      IV) Amazon Resource Name (ARN) copy it from Edit Bucket Policy and then paste it followed by a "/" and "*".  
      V) Then we will click on <b>Add Statement</b>.  
      VI) Then we will click on <b>Generate Policy</b>.  
      VII) Then we will <i>copy</i> the code.  
      VIII) Then we head back to the previous tab and then <b>paste the code</b> under "Policy".  
      IX) Then we click on <b>Save Changes</b>
