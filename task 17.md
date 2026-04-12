OBJECTIVE - The aim of this task was to create a MySQL database using AWS RDS and understand basic configuration like instance setup, security, and connectivity.

STEPS PERFORMED- 

1.)First, I opened AWS Console and searched for RDS (Relational Database Service).
Then I clicked on Create Database.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-29-34" src="https://github.com/user-attachments/assets/4ca4492a-9102-4bcd-b8af-c127d7e79079" />

2.)selected MySQL as the database engine because it is widely used and easy to understand.
Then I selected:
Full configuration 
Free tier (to avoid charges)
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-34-12" src="https://github.com/user-attachments/assets/9da5e412-6fc0-4970-be61-6b71dbc686e4" />

3.)selected Single-AZ deployment because Multi-AZ was not available for free tier.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-36-19" src="https://github.com/user-attachments/assets/8f448ea5-d48d-46a9-8a0a-63e16d8e4256" />

4.)Then I configured basic database details:
DB instance name: mydb-demo
Master username: admin
Created a strong password and than i selected self-managed credentials also.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-47-23" src="https://github.com/user-attachments/assets/bd66c937-2289-43c6-82ae-64ecdb78275f" />

5.)In next step, i configured - VPC , Public access , Security group , and we didnt connect the ec2 at this stage.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-49-57" src="https://github.com/user-attachments/assets/5d750bde-bb86-4f1c-b066-4fd928e908c5" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-51-03" src="https://github.com/user-attachments/assets/a340ff01-f655-411b-9669-096b1a962921" />

6.) Than , i have done additional configuration 
Initial database name , Monitoring kept default
No extra features enabled
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 14-52-16" src="https://github.com/user-attachments/assets/2ed489a0-b3f0-4124-ad6f-e5e00bb469e9" />

7.)Finally, I clicked on Create Database button.The database started creating and its status changed to Available after a few minutes.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 15-08-27" src="https://github.com/user-attachments/assets/11c31411-c9e4-421f-b572-f804bf408742" />

8.)After the database was created, I went to EC2 service and launched a new instance.
I selected:
- Amazon Linux 2023 AMI  
- Instance type: t3.micro (free tier)  
then I created/selected a key pair and allowed SSH access.
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 15-14-09" src="https://github.com/user-attachments/assets/3d2f0d61-aa85-4d7a-ae3f-1868a43b5eef" />

9.)After launching, I connected to the EC2 instance using EC2 Instance Connect and opened the terminal.
and used some commands
sudo yum update -y , sudo yum install mariadb105 -y , and than i wrote the actual endpoint and it was connected.
To verify the connection, basic MySQL commands can be used like:
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 15-41-08" src="https://github.com/user-attachments/assets/f980fffb-6db8-4d62-883d-85a82db5ae81" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 15-43-20" src="https://github.com/user-attachments/assets/f71365a4-c144-421e-81b0-cffd4f7125eb" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-12 16-14-01" src="https://github.com/user-attachments/assets/72f72e8d-0331-4d01-8b43-b398bf000ee4" />

RESULT-The RDS MySQL database was successfully connected with the EC2 instance, and queries were executed without any errors.











