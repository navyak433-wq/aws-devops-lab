OBJECTIVE:- Creating and Managing S3 Bucket using AWS CLI

STEPS PERFORMED:-
1.)Checking AWS CLI Installation
First, I checked whether AWS CLI was installed on my system by running the following command: (aws --version).
<img width="945" height="125" alt="Screenshot from 2026-04-03 15-55-15" src="https://github.com/user-attachments/assets/ea88083d-53bf-4da7-b1f4-fe89a08fdef5" />

2.)Configuring AWS CLI
Next, I configured AWS CLI using my IAM user credentials by running: aws configure
I entered the following details:
AWS Access Key ID
AWS Secret Access Key
Default region name (ap-south-1)
Default output format (json)
<img width="380" height="40" alt="Screenshot from 2026-04-03 15-58-52" src="https://github.com/user-attachments/assets/95f048ef-d6e7-4fba-897e-18159a9c480a" />
<img width="380" height="40" alt="Screenshot from 2026-04-03 15-58-52" src="https://github.com/user-attachments/assets/b661e429-c9da-430b-a33b-a651ad97b2ef" />

3.)Creating an S3 Bucket
After configuration, I created a new S3 bucket using the command: (aws s3 mb s3://navya-cli-bucket-78654).
<img width="935" height="123" alt="Screenshot from 2026-04-01 01-39-27" src="https://github.com/user-attachments/assets/681ecf9c-f5e9-4456-a8d9-ec44e3b851d7" />

4.)Verifying Bucket Creation
Then, I verified whether the bucket was created by listing all buckets: (aws s3 ls).
<img width="580" height="42" alt="Screenshot from 2026-04-03 16-03-15" src="https://github.com/user-attachments/assets/1a864f27-b1ad-42ed-a3bb-c0dce2101f8b" />

5.)Creating a Sample File
Next, I created a sample text file using: (echo "hello world" > test.txt).
<img width="663" height="45" alt="Screenshot from 2026-04-03 16-04-14" src="https://github.com/user-attachments/assets/2360ee4e-ba36-4897-b24d-dbb74e420108" />

6.) Uploading File to S3 Bucket
I uploaded the file to the S3 bucket using: aws s3 cp test.txt s3://navya-cli-bucket-78654.
<img width="665" height="65" alt="Screenshot from 2026-04-03 16-05-39" src="https://github.com/user-attachments/assets/34b0df82-f0ad-47a9-bdf7-d728127486fb" />

7.)Verifying File in Bucket
Then, I checked the contents of the bucket: aws s3 ls s3://navya-cli-bucket-78654.
<img width="659" height="65" alt="Screenshot from 2026-04-03 16-06-40" src="https://github.com/user-attachments/assets/ad834f66-2fda-4e55-8bc4-c0f158f09dab" />

8.)Deleting File from Bucket
After that, I deleted the file using: aws s3 rm s3://navya-cli-bucket-78654/test.txt.
<img width="971" height="82" alt="Screenshot from 2026-04-03 16-07-56" src="https://github.com/user-attachments/assets/0ed75754-0329-48a8-8cdc-bf4483def024" />

9.)Final Verification
Finally, I checked the bucket again: aws s3 ls s3://navya-cli-bucket-78654.
<img width="968" height="92" alt="Screenshot from 2026-04-03 16-09-49" src="https://github.com/user-attachments/assets/f739a8a2-ec0e-43b1-8353-92edbe5315a8" />

RESULT:-Successfully created and managed an S3 bucket using AWS CLI, including uploading and deleting files.









