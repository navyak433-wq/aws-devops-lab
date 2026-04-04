OBJECTIVE-  Create S3 Bucket with Limited Public Access (images only).

STEPS PERFORMED:-

1.)First, I went to AWS S3 service and created a new bucket named navya-images-bucket. I kept all the default settings while creating the bucket.-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 14-08-09" src="https://github.com/user-attachments/assets/691b22b3-3450-47b5-8b6c-9211edb8ef02" />

2.)After creating the bucket, I opened it and created a folder named images inside the bucket.-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 14-10-14" src="https://github.com/user-attachments/assets/effc60b5-2169-40b8-b86a-254a40dd954b" />

3.)Then I opened the images folder and uploaded an image file inside it using the upload option.-
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 14-21-18" src="https://github.com/user-attachments/assets/647cf473-d416-4f73-8748-9f9a48ab0419" />

4.)Next, I went to the Permissions tab and edited Block Public Access settings.
I adjusted the settings so that controlled public access can be allowed using bucket policy.
<img width="1229" height="158" alt="Screenshot from 2026-04-04 14-38-32" src="https://github.com/user-attachments/assets/f169ddff-efc4-4466-832d-2d2e06c9ddc9" />

5.)Add Bucket Policy
After that, I added a bucket policy to allow public read access only for the /images/ folder.
<img width="494" height="389" alt="Screenshot from 2026-04-04 14-41-35" src="https://github.com/user-attachments/assets/a7c80cce-c5fe-4d05-92af-a413d5cf2871" />
<img width="563" height="177" alt="Screenshot from 2026-04-04 14-45-36" src="https://github.com/user-attachments/assets/0bd3bfcf-1153-46c0-ab73-4ebb33f78f6f" />

6.)Finally, I opened the uploaded image using its Object URL in the browser.
The image opened successfully, which confirms that public access is working only for the images folder.
<img width="1920" height="1200" alt="Screenshot from 2026-04-04 14-47-47" src="https://github.com/user-attachments/assets/f50bf230-03c6-4323-bb28-b0ffa33fd22e" />

RESULT-The image was successfully accessed using the Object URL, confirming that only the /images/ folder has public access while the rest of the bucket remains private.


