OBJECTIVE- Implement Private EC2 with S3 Access via VPC Endpoint
Create Gateway VPC Endpoint for S3
Remove NAT Gateway
Ensure private EC2 can:
-Access S3
- Cannot access internet
Validate using CLI

STEPS PERFORMED - 

1.) Created a private subnet in the VPC with a non-overlapping CIDR block.
<img width="1375" height="724" alt="Screenshot from 2026-04-26 19-25-43" src="https://github.com/user-attachments/assets/b7540c6b-70a3-41a1-9895-0a279df9b1fe" />

2.) Created a route table and associated it with the private subnet. Verified that the route table contains only the local route and no internet gateway route, ensuring the subnet is private.
<img width="1212" height="726" alt="Screenshot from 2026-04-26 19-28-19" src="https://github.com/user-attachments/assets/cdd26539-e9f9-4daf-94a2-6e32cb2b93a6" />
<img width="1345" height="696" alt="Screenshot from 2026-04-26 19-28-50" src="https://github.com/user-attachments/assets/1ffa20fd-017f-4867-877f-720a075fbf54" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-26 19-29-26" src="https://github.com/user-attachments/assets/d801abb8-8bba-404b-8569-385a01d75cf2" />
<img width="1914" height="991" alt="Screenshot from 2026-04-26 19-29-45" src="https://github.com/user-attachments/assets/a427911d-81d4-42f3-a845-0e77beb07463" />

3.) Launched an EC2 instance in the private subnet with no public IP and attached an IAM role (EC2-S3-Role) with S3 access permissions.
<img width="1336" height="704" alt="Screenshot from 2026-04-26 19-36-18" src="https://github.com/user-attachments/assets/c26ba28d-1abf-4a23-858e-cfaf5f019b7f" />
<img width="1332" height="720" alt="Screenshot from 2026-04-26 19-36-49" src="https://github.com/user-attachments/assets/d71c1437-6d69-48ae-9017-41ec87cb16e3" />
<img width="1861" height="798" alt="Screenshot from 2026-04-26 19-35-42" src="https://github.com/user-attachments/assets/8960e4cf-7807-4e79-b7c7-3be53373d142" />

4.)Created a Gateway VPC Endpoint for Amazon S3 and associated it with the private route table to enable private access to S3.Successfully created a Gateway VPC Endpoint for Amazon S3.
The endpoint is in “Available” state and associated with the private route table.
<img width="1919" height="1035" alt="Screenshot from 2026-04-26 19-40-48" src="https://github.com/user-attachments/assets/d73fe48b-243a-494c-b15c-208a5af6557b" />
<img width="1915" height="1001" alt="Screenshot from 2026-04-26 19-41-55" src="https://github.com/user-attachments/assets/521e7017-b6b1-403c-b55e-4ce0edb4cec9" />

5.) Created Interface VPC Endpoints for ssm, ec2messages, and ssmmessages, configured with private subnet and security group allowing HTTPS traffic to enable Session Manager access.
I verified ssm related vpc endpoints are in available state.
<img width="1914" height="1046" alt="Screenshot from 2026-04-26 19-54-06" src="https://github.com/user-attachments/assets/b3072d7c-ced0-461b-a7dc-2d22d3ad7ae1" />

6.) Connected to the instance using SSM Session Manager
Ran the following commands- ping google.com , curl https://google.com
Both requests failed  and timed out, confirming that 
No NAT Gateway
No internet access from private subnet
<img width="918" height="43" alt="Screenshot from 2026-04-26 20-41-06" src="https://github.com/user-attachments/assets/8421a7c3-3c6d-4edc-928d-730e572d73dc" />

7.) Validated S3 access using AWS CLI
Ran the following command - aws s3 ls
Successfully listed S3 buckets:- my-private-test-bucket-123
<img width="704" height="234" alt="Screenshot from 2026-04-26 20-45-27" src="https://github.com/user-attachments/assets/0466756c-3373-4184-8716-cb25bba8e9ce" />

RESULT - The objective of enabling secure private access to S3 without internet connectivity was achieved successfully.











