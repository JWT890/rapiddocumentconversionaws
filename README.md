# rapiddocumentconversionaws

Converting documents from one source, such as docx or doc, can be quite the time trying to get to convert to pdf and vice versa. With AWS, there are tools available in use for such a thing that doesn't take as long.  
The AWS features required for use in this are:  
AWS Lambda: service that lets you run code without any provisions or management. Does all the administration for you  
Amazon S3: object storing service where you can create buckets to store data or folders for scalability, security, availability and performance. 
Cloudwatch: Used to monitor and track resources in real time and track/display metrics for use.  
Amazon Translate: Neural network machine useful for high-quality and afforable language translation automation.  
and AWS IAM: service that manages users, access, and permissions based on role and application use (similar to Active Directory.  

First step is to go the IAM center and set up a role with the relevant permissions with this:
Relevant permissions are: 
