OBJECTIVE-Configure Server Access Logging in Amazon S3

STEPS REQUIRED-

1.)First, I created a main S3 bucket named navya-main-bucket in the ap-south-1 region.
I kept the default settings and made sure that Block Public Access is enabled.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-12-58" src="https://github.com/user-attachments/assets/310b4d9e-2784-4096-a253-aa7a1a938931" />

2.)After that, I created another S3 bucket named navya-logs-2026 which will store the logs of the main bucket.
Same region (ap-south-1)
Block Public Access enabled so that logs remain private
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-14-44" src="https://github.com/user-attachments/assets/de20f2b3-1879-4bc4-8203-108f846f91a1" />

3.)Then I opened the main bucket navya-main-bucket.
I went to the Properties tab of the main bucket and found the Server Access Logging section.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-33-27" src="https://github.com/user-attachments/assets/728096b7-0cce-4993-a913-68aa2001489e" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-33-58" src="https://github.com/user-attachments/assets/536e058b-4791-4c23-9268-53be063b3826" />

4.)Then I clicked on Browse S3 and selected navya-logs-2026 as the destination bucket.
After selecting the logs bucket, I clicked on Save changes.
A success message was displayed showing that server access logging was enabled.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-23-10" src="https://github.com/user-attachments/assets/ee9b3d3e-4119-4281-97d9-a2e3e2b8ecb9" />

5.)Finally, I opened the logs bucket (navya-logs-2026) and checked the Objects tab.
It is empty initially because logs are generated after some activity.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-24-25" src="https://github.com/user-attachments/assets/b10ea63c-aeb4-45c6-8ced-2fe2828687fe" />

6.)I also verified in the Permissions tab of logs so that to check :-
Block Public Access is ON
Bucket is not publicly accessible
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 17-38-30" src="https://github.com/user-attachments/assets/1e6aa0c5-98f2-4c63-bf4b-dc745e20a742" />

RESULT-Server access logging was successfully enabled on the main bucket, and all logs are being stored in a separate secure bucket.




