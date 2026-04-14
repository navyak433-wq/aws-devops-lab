OBJECTIVE - The objective of this project is to implement a Disaster Recovery (DR) system using AWS services.

STEPS PERFORMED-

1.) Open AWS S3
Click on Create Bucket
Enter bucket name - source bucket (dr-source-bucket)
Select region , and i also enable Versioning.
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-38-29" src="https://github.com/user-attachments/assets/3d0a9fad-d7b7-487c-8ff9-1de763358673" />

2.) Create another bucket
Choose a different region (e.g., Singapore)
Enable Versioning , it was a destination bucket
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-43-06" src="https://github.com/user-attachments/assets/74d918a7-d3fa-478c-8de5-9cd3296086ba" />

3.) Than  i have , Open source bucket
than went  to Management after that scroll down to  Replication rules
than i have Create rule:
Select destination bucket
Choose IAM role (auto-created)
Apply to entire bucket
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-47-40" src="https://github.com/user-attachments/assets/2d7510b4-ed52-4292-85b4-67c01ba74124" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-49-36" src="https://github.com/user-attachments/assets/e3c0702f-d1bc-4023-80f8-c598430fd219" />

4.) Upload a file in source bucket
Check destination bucket to see that same file is uploaded automatically there.
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-50-51" src="https://github.com/user-attachments/assets/70ec5fca-f3db-4ee5-985f-1d2e7e224944" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 13-52-34" src="https://github.com/user-attachments/assets/c9b96e04-30d8-453b-99ab-2316adeb7669" />
and it was sucessfully uploaded there so Files are automatically copied from one region to another.

5.) Than we create database so, Go to RDS  than we click Create database , Select MySQL , Choose Free tier , Enter DB name (e.g., dr-db) , Set username and password.
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-00-36" src="https://github.com/user-attachments/assets/1399a061-bd6d-42e4-8ec3-93033bcd7cf6" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-08-13" src="https://github.com/user-attachments/assets/b35b88eb-9495-4b35-82a3-1d163fe12465" />

6.) Than we Create Read Replica after that we Select primary DB than after that we Click Actions  and after that we click  Create read replica after that we Choose different region and that Keep default settings
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-11-44" src="https://github.com/user-attachments/assets/df37f5f8-6835-4962-847c-a0b0543161ae" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-31-45" src="https://github.com/user-attachments/assets/f9280110-1563-4d02-9d04-4c4ce531262f" />
And a  read replica is created in another region for backup and failover.

7.) Than we promote replica Select replica that we Click Actions  and click Promote and than Confirm promotion.-
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-38-42" src="https://github.com/user-attachments/assets/a81c6ca6-827b-4658-8560-a31e65dfdd51" />

8.) After that Replica becomes independent database and it No longer shows “Replica”.
<img width="1920" height="1200" alt="Screenshot from 2026-04-14 14-45-33" src="https://github.com/user-attachments/assets/08ad9ad0-45c5-407d-8c7e-73bb85945de6" />

RESULT-Disaster Recovery system was successfully implemented using AWS.












