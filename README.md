# rapiddocumentconversionaws

Converting documents from one source, such as docx or doc, can be quite the time trying to get to convert to pdf and vice versa. With AWS, there are tools available in use for such a thing that doesn't take as long.  
Features used to do so:  
S3:  
Lambda:  
IAM:  

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


