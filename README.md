# Receipts-Organizer
 An automated receipts organizing tool that help to keep track of all the receipts
AWS services : 
Amazon S3 - to upload an store receipt files
Amazon textract - to extract details
dynamoDB - to save and organise important data
SES - to send email summaries
Lambda - to automate the whole thing
IAM - ensure secure access between services 

Created a S3 bucket inside that created a folder incoming for new receipts
dynamoDB create table which stores all the extracted data in structured format
SES — create identity — email —- verification email 
IAM — create role — for the service lambda 
Policies - S3read , textractfull access , dynamodbfull access, lambda execution, sesfull

Create lambda function - and join the role 
Go to configuration and change the timeout 
Add env variables - sender mail with value , recipient mail , dynamodb 

Add the code in lambda 

Go to S3 properties of created bucket - allow event notifications –create event notification 
Attach S3 to lambda 

FOR EXECUTION - select receipt and upload in s3 bucket folder 
After uploading go to lambda to check fuc is triggered 
Go to monitor tab 
Or go to dynamo db where receipt data gets stored 
And check email 
