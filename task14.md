OBJECTIVE-The objective of this task is to host a static website using Amazon S3 by configuring a bucket, enabling website hosting, and making the content publicly accessible.

STEPS PERFORMED-
1.)I logged into AWS and opened the S3 service. Then, I clicked on “Create Bucket” and provided a unique bucket name.
I selected the region and disabled the “Block all public access” option to allow public access later.
<img width="1371" height="822" alt="Screenshot from 2026-04-11 10-22-25" src="https://github.com/user-attachments/assets/0718c1e1-144c-4b45-99cb-485fd27f1cf8" />

2.)After creating the bucket, I enabled versioning from the Properties tab. 
This ensures that multiple versions of files are maintained and can be restored if needed.
<img width="1907" height="952" alt="Screenshot from 2026-04-11 10-29-15" src="https://github.com/user-attachments/assets/d10b7c2d-3b64-4fc3-9bc8-f5e89d135593" />

3.)Next, I went to the Properties tab and enabled static website hosting.
I selected Host a static website and set the index document as index.html.
<img width="1383" height="713" alt="Screenshot from 2026-04-11 10-31-41" src="https://github.com/user-attachments/assets/0e329e77-ff08-4b09-abc3-aeaabed59f3b" />

4.)created an HTML file named index.html and uploaded it in the Objects section of the bucket.
<img width="1404" height="773" alt="Screenshot from 2026-04-11 10-34-06" src="https://github.com/user-attachments/assets/234886b3-21b2-4886-be0b-dd71bf2ad6f9" />

5.)created an HTML file named index.html and uploaded it in the Objects section of the bucket. so this is my output-
<img width="1381" height="576" alt="Screenshot from 2026-04-11 10-35-32" src="https://github.com/user-attachments/assets/eff7e3da-d374-4833-986c-4dccf0c40512" />

6.)Finally, I copied the website endpoint URL from the Properties tab and opened it in the browser. The website was showed  successfully.
<img width="1332" height="412" alt="Screenshot from 2026-04-11 10-36-31" src="https://github.com/user-attachments/assets/ad451840-3ac7-4410-b571-1bc5138ed0aa" />

so,the result is The static website was successfully deployed using Amazon S3.




