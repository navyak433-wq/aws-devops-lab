OBJECTIVE-Configure Secure S3 Bucket with Restricted Access

STEPS PEROFRMED:-

1.)First, I created a new S3 bucket from the AWS console-
I named the bucket navya-secure-bucket and kept all default settings.
I also kept Block Public Access ON initially while creating the bucket.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 14-59-53" src="https://github.com/user-attachments/assets/5f55c84b-172c-4566-b0bf-2bb41237c454" />

2.)After creating the bucket, I opened it and created a folder named uploads-
This folder will be used to allow uploading files based on the policy.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 15-00-46" src="https://github.com/user-attachments/assets/36ad2f5b-26ef-4a52-991c-8f4b7f47f81b" />

3.)Next, I went to the Permissions tab and edited the Block Public Access settings.
I turned OFF all the options so that the bucket policy can be applied properly.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 15-05-34" src="https://github.com/user-attachments/assets/63b03cc3-57b6-4db4-90cd-49071ba847b4" />

4.)Then, I added a custom bucket policy to control access. The policy includes-
Allow uploading files only inside the uploads/ folder
Deny deletion of any object in the bucket
Deny uploads if server-side encryption is not enabled
After adding the JSON policy, I saved the changes successfully , so this was the final output.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 15-06-27" src="https://github.com/user-attachments/assets/b8a2aa39-1970-4277-8954-4b0cb0b995a0" />

5.)When I tried to delete the object, it showed “Access Denied”. This means the delete restriction is working properly as per the bucket policy.-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 15-24-37" src="https://github.com/user-attachments/assets/0a89feb9-835f-42df-99d3-10967cd20b4d" />


RESULT-The S3 bucket policy was successfully configured to allow uploads only in the /uploads/ folder, deny deletion, and enforce server-side encryption.

