OBJECTIVE-Create S3 Bucket and Configure Access Control

STEPS PERFORMED-

1.)Create S3 Bucket-
First, I went to the AWS S3 service and created a new bucket.
I gave a unique name: navya-s3-bucket-2026 and kept other settings as default.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 13-05-28" src="https://github.com/user-attachments/assets/5474919a-9fa4-4576-89fe-f81784a4f39b" />

2.)Disable Block Public Access-
After creating the bucket, I opened the Permissions tab.
Then I edited Block Public Access settings and turned it OFF to allow public access.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 13-06-35" src="https://github.com/user-attachments/assets/e0168297-6903-485d-ba85-d687ddf4e59f" />

3.)After disabling block public access, I added a bucket policy to allow public read access.-
This policy allows anyone to access the objects inside the bucket.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 13-19-17" src="https://github.com/user-attachments/assets/2e533d2b-da07-4a1e-a176-b459409acddd" />

4.)Create IAM User-
Then I created a new IAM user named navya-user from IAM service.
I did not attach any permissions to this user (kept it default).
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 13-28-10" src="https://github.com/user-attachments/assets/bb2ea94a-d1ae-45b7-909d-be486ce7518e" />

5.)Add Restricted Access (User + IP)
After that, I updated the bucket policy again to:
Allow access only to navya-user
Restrict access using my IP address<img width="1920" height="1200" alt="Screenshot from 2026-04-04 13-30-05" src="https://github.com/user-attachments/assets/b5568a10-169f-4a9a-91ac-79b4c7c855c8" />

RESULT-I successfully created an S3 bucket and configured public and restricted access using bucket policies and IAM user.





