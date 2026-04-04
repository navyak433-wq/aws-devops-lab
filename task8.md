OBJECTIVE:-The objective of this task was to create a lifecycle rule in an S3 bucket to automatically manage files and reduce storage cost.

STEPS PERFORMED:-

1.)I logged into AWS and opened the S3 service-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-37-26" src="https://github.com/user-attachments/assets/5350a77f-0a72-40fa-9c4d-ee0cb41b7fed" />

2.)After that, I went to the Management tab and selected Create lifecycle rule-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-38-10" src="https://github.com/user-attachments/assets/e3ddf31f-a3d3-4fe4-80ea-8e8288e3a8a9" />

3.)I entered the rule name as uploads-smart-lifecycle and added the prefix uploads/ to apply the rule only to that folder and Then I configured the transition rules-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-41-12" src="https://github.com/user-attachments/assets/cec308d5-a5fe-4c3d-bcf0-11e349b88d69" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-42-32" src="https://github.com/user-attachments/assets/fd7f54e7-1d24-424d-a2a9-5c54a040b022" />

4.)After that, I enabled expiration and set the value to 365 days-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-43-34" src="https://github.com/user-attachments/assets/180a035e-9ab0-4f27-bc9f-e76e78acf907" />

5.)Finally, the lifecycle rule was successfully created and visible in the bucket-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 12-44-56" src="https://github.com/user-attachments/assets/23bafa90-62e2-4bb6-8daf-f6e94d7eb625" />

RESULT:-The lifecycle rule was created successfully and is working as expected.





