# rapiddocumentconversionaws

Converting documents from one source, such as docx or doc, can be quite the time trying to get to convert to pdf and vice versa. With AWS, there are tools available in use for such a thing that doesn't take as long.  
Features used to do so:  
S3:  Object storage service that offers scalability, availablity, security, and performance  
Lambda: Automatically runs your code without any provisioning or server management  
IAM: Used for managing roles, access, and permissions for users and groups based off access  

First step is to create a role in IAM: head to access management -> roles then click on create role  
For use case choose Lambda, skip the permissions for now, and name the role lambda-s3-execution-role.  
Next click on the role and click on add permissions and click on add inline policy, chose lambda and switch to JSON.  
Delete the code their and paste this code: 
{    
  "Version": "2012-10-17",  
  "Statement": [  
    {  
      "Effect": "Allow",  
      "Action": ["s3:GetObject", "s3:PutObject"],  
      "Resource": [  
        "arn:aws:s3:::document-upload-bucket/*",  
        "arn:aws:s3:::document-output-bucket/*"  
      ]  
    },  
    {  
      "Effect": "Allow",  
      "Action": ["logs:*"],  
      "Resource": "*"  
    }  
  ]  
}  
![image](https://github.com/user-attachments/assets/7523d6db-1632-4ff7-8862-7b735d8dd125)  

After pasting it, save the permission policy as lambda execution.  

Second step is to create the S3 Buckets for input/upload and the output bucket. Go to S3 and click on create a bucket.  
Name the input/upload bucket as input.bucket.1documents and the output bucket as output.1.bucketdocuments.  
![image](https://github.com/user-attachments/assets/f79b26bb-b67e-46f2-9320-7444fe48608f)

Third step is to head over to Lambda and create a function. Click on create function and name the function convert_documents. Next click on the drop down arrow for change default execution role.  
For execution role, click on use an existing role and choose the role you created in the first step, should look like this:  
![image](https://github.com/user-attachments/assets/74cdc449-ecff-4d63-82e5-15943040b98a)  
Then create the function which should take you here:  
![image](https://github.com/user-attachments/assets/2f74d40d-051e-4d2b-8989-7e0cb6d32706)  

Next select the create a trigger and choose S3 as the source and the bucket as the input bucket and click add


