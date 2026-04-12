OBJECTIVE- The aim of this task was to understand and implement IAM best practices in AWS by creating groups, assigning permissions, and improving security.

STEPS PERFORMED-

1.)First, I created three IAM groups:
Admin
Dev
ReadOnly
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 11-15-31" src="https://github.com/user-attachments/assets/9544c542-1708-4f7a-a120-da0aa941c8af" />

2.)After creating the groups, I attached policies:-
.Admin Group
Attached policy : AdministratorAccess
This provides full access to AWS services.<img width="1920" height="1200" alt="Screenshot from 2026-04-12 02-00-39" src="https://github.com/user-attachments/assets/768ec93e-aaf6-4518-bff5-ce7a272c5797" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 02-02-42" src="https://github.com/user-attachments/assets/6723b87b-a72c-40b1-bedf-41afd04e666a" />

.Dev Group
Attached policiy : AmazonEC2FullAccess and AmazonS3FullAccess
This allows developers to work with EC2 instances and S3 storage 
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 02-02-13" src="https://github.com/user-attachments/assets/0ef331fe-b758-4c27-9c0b-d2d0d8b84045" />
<img width="1081" height="652" alt="Screenshot from 2026-04-12 11-39-43" src="https://github.com/user-attachments/assets/4184d126-0422-482e-bdd6-f49d941574f4" />

.Readonly group
Attach policiy :Readonly access
The user can only view resources and not make changes.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 10-32-51" src="https://github.com/user-attachments/assets/5cefe94e-d5d9-41c1-ab16-45ff224e5769" />

After that, I assigned users to different groups:
One user in Admin group
One user in Dev group
One user in ReadOnly group
dev group (Navya user)-<img width="1920" height="1200" alt="Screenshot from 2026-04-12 10-41-41" src="https://github.com/user-attachments/assets/53139de7-8f7d-418f-a492-e22944f9a90f" />
admin group (avika)-<img width="1920" height="1200" alt="Screenshot from 2026-04-12 11-01-48" src="https://github.com/user-attachments/assets/b35301ff-da72-4da2-afa4-3e8ae081e477" />
readonly group (aditi)-<img width="1920" height="1200" alt="Screenshot from 2026-04-12 11-10-59" src="https://github.com/user-attachments/assets/70f8d16d-f7d5-48be-b4b2-b146bdd57206" />
and i have done  For better security, Multi-Factor Authentication (MFA) was enabled for the root user.

3.)First, I created an S3 bucket with a unique name.
Inside the bucket, I created a folder named private which will be used for restricted access.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 12-01-39" src="https://github.com/user-attachments/assets/05d8325c-6503-457e-9ef8-9620c3792870" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 12-05-38" src="https://github.com/user-attachments/assets/25a78446-34b4-4d53-8dad-3b040dceb195" />

so than ,  I created a custom IAM policy using JSON. This policy allows access only to the private folder inside the bucket and restricts access to other parts of the bucket.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 12-11-59" src="https://github.com/user-attachments/assets/ab8c301a-4ab9-4924-bd91-bcb9fdf3a294" />

than after that,Then, I saved the policy with the name S3RestrictedAccess. After that this policy to the required user/group so that the user can only access the restricted folder. so this was my output
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 12-22-37" src="https://github.com/user-attachments/assets/280c26f1-922f-4610-9300-6607e1ff924b" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 12-22-37" src="https://github.com/user-attachments/assets/d1e3c62d-61bb-45f7-971f-a66d19390bfa" />

RESULT-IAM groups and permissions were successfully configured and users were managed securely using best practices.








