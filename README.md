# rapiddocumentconversionaws

Converting documents from one source, such as docx or doc, can be quite the time trying to get to convert to pdf and vice versa. With AWS, there are tools available in use for such a thing that doesn't take as long.  
The AWS features required for use in this are:  
AWS Lambda: service that lets you run code without any provisions or management. Does all the administration for you  
Amazon S3: object storing service where you can create buckets to store data or folders for scalability, security, availability and performance. 
Cloudwatch: Used to monitor and track resources in real time and track/display metrics for use.  
Amazon Translate: Neural network machine useful for high-quality and afforable language translation automation.  
and AWS IAM: service that manages users, access, and permissions based on role and application use (similar to Active Directory.  

First step is to go the IAM center and head to access management -> roles then click create role:  
For trusted entity type choose AWS service and use case choose S3.  
Next go to add permissions and choose AmazonS3FullAccess, TranslateFullAccess, and CloudWatchFullAccess  
Then click to create role and head on to the next step.  
The Role should look like this:  
![image](https://github.com/user-attachments/assets/f9eba2a5-d8ea-46ec-90e0-98fb7f8555d7)  


Second step is to head to S3 and create two S3 Buckets for input and output respectively  
![image](https://github.com/user-attachments/assets/26f4a381-6e0f-42b3-b840-f0cf2461b84f)  
