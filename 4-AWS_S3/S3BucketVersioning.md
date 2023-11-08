This will be done at the bucket level.  
Any file that is not versioned prior to enabling versioning will be versioned as "null".  

Steps for Bucket Versioning:  

Step_1) Head over to Permissions and click "Edit" on Bucket Versioning.  
    I) We have to click on Enable.  

Step_2) After this we head back to the index.html file and modify it to (I "Really" Love Coffee).  
    I) Then we re-Upload the index.html file.  
    II) Then if we toggle the <b>"Show versions"</b> button, then we will see the versions of the files uploaded.  

Note: 
If we delete a file, and the show versions was on then, we get the option to permanently delete.  
Otherwise, if the show version is turned off, we donot delete the actual file and get option to "delete marker".  
![Screenshot (1594)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/ad1274a2-2ea3-466d-9552-e7bd86945e21)

After the deletion, if we turn on the show version, the file that we deleted when show version was off, it shows delete marker with a version id.  
![Screenshot (1595)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/b92712b5-4d05-4e4e-a432-0d7ffa85fdcc)  

Now if we click on the delete marker and delete it, we will get the original version of the file back.  
i,e. if we permanently delete the delete marker, the result will be that our original file we be restored.
![Screenshot (1596)](https://github.com/Faysal-Ezaz/Project_AWS/assets/95119493/64b8dab6-d281-4f6b-b552-4aa3e2a5be1d)  


