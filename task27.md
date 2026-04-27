OBJECTIVE - To understand and implement AWS IAM policies by allowing and denying specific actions on services like EC2, S3, and VPC, in order to control user access and enhance cloud security.

STEPS PERFORMED :-

1.) To allow all EC2 actions for a user except terminating an instance.
Go to IAM than i went to  Policies than i  Create Policy
Select EC2 service
Allow all actions (ec2:*)
Add a separate statement to Deny:
Action: ec2:TerminateInstances
Attach this policy to the user
Login with that user and test termination
so the output was 
<img width="1230" height="524" alt="Screenshot from 2026-04-27 18-10-34" src="https://github.com/user-attachments/assets/bd76766c-9101-45b9-809c-2fc191568263" />
When i was trying to terminate instance . The  Access Denied error shown.

2.)To allow access to all S3 buckets except one specific bucket.
Go to IAM than i went to Policies than i created  Create Policy
Allow:
s3:- on all resources
Add Deny statement:
Action: s3:*
Resource: specific bucket ARN
Attach policy to user
Try accessing restricted bucket
<img width="1313" height="356" alt="Screenshot from 2026-04-27 18-12-32" src="https://github.com/user-attachments/assets/a93533f3-9813-4854-a846-c7ace1888c2f" />
so the Bucket shows “Insufficient permissions” error.

3.)To allow EC2 start/stop actions but restrict them in a specific region.
Create IAM policy
Than i Allow:
ec2:StartInstances
ec2:StopInstances
Add Deny condition:
Region (e.g., us-east-2)
Attach policy to user
Test in allowed vs restricted region
<img width="1169" height="342" alt="Screenshot from 2026-04-27 18-15-38" src="https://github.com/user-attachments/assets/b765a586-d3e6-4d95-b561-9de18bb88b51" />
In restricted region the  Operation denied
In allowed region the  Works normally.

4.)To allow creation of VPC but restrict Internet Gateway creation.
Steps that i performed 
Create IAM policy
Allow:
ec2:CreateVpc
Deny:
ec2:CreateInternetGateway
Attach to user
Test both actions
<img width="1080" height="507" alt="Screenshot from 2026-04-27 18-17-24" src="https://github.com/user-attachments/assets/58ec4682-f362-4ae0-bf95-d8a065b394ca" />
so ,the  User can create VPC but cannot create Internet Gateway.

5.) To prevent deletion of S3 objects while allowing all other actions.
Steps that i performed 
Create IAM policy
Allow:
s3:*
Deny:
s3:DeleteObject
s3:DeleteBucket
Attach policy
Try deleting objects
so the output was 
<img width="1014" height="397" alt="Screenshot from 2026-04-27 18-19-34" src="https://github.com/user-attachments/assets/b3453591-20a7-49c5-9640-90ee98d766c8" />

RESULT- All tasks were successfully implemented using IAM policies.
The user was able to perform allowed actions while restricted actions were denied as expected, demonstrating that explicit deny rules override allow permissions and help enforce secure access control in AWS.






