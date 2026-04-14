OBJECTIVE- In this task, I implemented a centralized logging system using AWS services. The goal was to collect logs from different services and store them in a single S3 bucket. This helps in monitoring, debugging, and managing logs efficiently.

STEPS PERFORMED- 

1.)Opened AWS Console → S3
Clicked on Create bucket and done the further configuration -
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 16-39-06" src="https://github.com/user-attachments/assets/05f758f5-258b-4c9a-9f82-dfdc70a4779c" />

2.) Next, I enabled VPC Flow Logs to capture network traffic.
Went to VPC Dashboard  Your VPCs
Selected VPC (my-vpc)
Clicked on Create Flow Log
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 16-43-12" src="https://github.com/user-attachments/assets/439ae83c-c6ca-47c0-9292-2f29b7cb3f46" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 16-43-57" src="https://github.com/user-attachments/assets/774c2b59-abc2-4821-9478-46f2b4ff0751" />

3.) Enabling AWS CloudTrail
CloudTrail was used to log API activity.
Opened CloudTrail → Create Trail
 name: central-trail
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 16-51-11" src="https://github.com/user-attachments/assets/2ca9d309-f941-4e98-8b28-f73238835d9a" />

4.)nitial configuration of Application Load Balancer
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 17-12-24" src="https://github.com/user-attachments/assets/1a6397dd-9b50-4b6f-9da3-3454d486b8a5" />
This setup ensures that when the load balancer is fully deployed, its logs can be automatically stored in the centralized S3 bucket along with other logs.

5.) To manage storage and avoid unnecessary cost, I created a lifecycle rule.
Opened S3 bucket - Management tab
Clicked on Create lifecycle rule
Rule name- log-cleanup
Applied to all objects
Enabled-
Expire current versions of objects
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 17-01-22" src="https://github.com/user-attachments/assets/db95a7b2-f406-45db-8e1f-605e58c0f781" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 16-59-34" src="https://github.com/user-attachments/assets/911c359c-108d-4204-a85f-75bd5f49d452" />

RESULT-After completing all steps the Logs from VPC Flow Logs and CloudTrail are stored in a single S3 bucket
Logs are automatically deleted after 60 days
System is cost-efficient and easy to manage.




