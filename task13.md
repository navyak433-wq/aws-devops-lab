OBJECTIVE- The objective of this task was to enable data protection features in Amazon S3 by using Versioning, Object Lock, and bucket policies to prevent deletion of important files.

STEPS PERFORMED-

1.)First, I created a new S3 bucket named navya-lock-bucket-2026 in the Mumbai region.
While creating the bucket, I enabled:
Versioning
Object Lock
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-38-52" src="https://github.com/user-attachments/assets/7c73f1c2-4bc0-4706-8a71-71f84c1c4bed" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-40-02" src="https://github.com/user-attachments/assets/203e9d7b-8799-45b4-8a16-fe79b1fcec8d" />
Since Object Lock works only with versioning, so both i enable together.


2.)After creating the bucket, I went to the Properties section and opened Object Lock settings.
I enabled:
Default retention
Governance mode
I also set a retention period (in days), which ensures that objects cannot be deleted or modified during that time.
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-42-39" src="https://github.com/user-attachments/assets/8b9b5143-7333-48bb-adc1-ca78fcd22169" />

3.)Next, I created a folder named finance/ inside the bucket.
Then I uploaded a sample file into this folder to test the restrictions.
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-44-05" src="https://github.com/user-attachments/assets/0a27af87-6996-444d-8297-0aea49b3a049" />

4.)After uploading the file, I went to the Permissions tab and added a bucket policy.
The policy denied the s3:DeleteObject action for all objects inside the finance/ folder.
This was done to add an extra layer of protection on top of Object Lock.
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-44-53" src="https://github.com/user-attachments/assets/88493bfb-59a3-4fc6-b81a-9c71153bf76c" />

5.)To verify the configuration, I tried to delete the file from the finance/ folder.
The delete operation failed and showed an Access Denied error.
This confirmed that:
Bucket policy is working correctly
Object Lock is also preventing deletion
<img width="1920" height="1200" alt="Screenshot from 2026-04-05 08-49-12" src="https://github.com/user-attachments/assets/9e28c178-7af1-4c76-96b0-70dd2efa3597" />

RESULT-I enabled versioning and object lock and restricted deletion in the finance folder. The delete action showed “Access Denied”, so the setup is working properly.





