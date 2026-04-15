OBJECTIVE - In this task, I tried to create a secure way to access EC2 without using a bastion host.

STEPS PERFORMNED :-

1.) First, I launched an EC2 instance using Amazon Linux.
While creating it, I disabled the public IP so that it becomes a private instance.
<img width="1920" height="1200" alt="Screenshot from 2026-04-15 19-47-13" src="https://github.com/user-attachments/assets/919abaf4-9e47-46f6-bcbb-be615965377f" />
<img width="1914" height="977" alt="Screenshot from 2026-04-15 19-48-55" src="https://github.com/user-attachments/assets/c99003e7-e5c7-4a4f-bc9d-1e1c7e576408" />

2.) Then I created an IAM role and attached the policy AmazonSSMManagedInstanceCore. This is required so that EC2 can connect with Systems Manager.
<img width="1919" height="437" alt="Screenshot from 2026-04-15 19-51-21" src="https://github.com/user-attachments/assets/6edc8a36-5ed8-4a3c-89a6-c86c2533c7ce" />
<img width="1919" height="971" alt="Screenshot from 2026-04-15 19-50-42" src="https://github.com/user-attachments/assets/50266d28-7b2d-4b58-97e0-958cf07260fe" />
<img width="1911" height="992" alt="Screenshot from 2026-04-15 19-52-31" src="https://github.com/user-attachments/assets/55c17636-f62b-4d2f-ab34-77b574df3e0a" />
<img width="1737" height="908" alt="Screenshot from 2026-04-15 19-51-58" src="https://github.com/user-attachments/assets/e1667dc4-5253-4294-9375-29e4b98b35cf" />

3.) Then i connected it to my ec2 instance .
<img width="1919" height="684" alt="Screenshot from 2026-04-15 19-55-36" src="https://github.com/user-attachments/assets/d70b533d-f120-4c27-88fe-24b397d60abe" />
<img width="1913" height="1010" alt="Screenshot from 2026-04-15 19-56-00" src="https://github.com/user-attachments/assets/e751c1ec-2a6c-4474-9732-bd793c081c5f" />

4.) Initially, I was not able to connect because the instance had no internet access. So I assigned an Elastic IP temporarily.
<img width="1357" height="645" alt="Screenshot from 2026-04-15 20-44-48" src="https://github.com/user-attachments/assets/763da6b5-f407-447a-bf0f-16c52d360331" />

5.) After giving internet access, I was able to connect to the EC2 using Session Manager. It opened a terminal directly in the browser. 
<img width="1920" height="1200" alt="Screenshot from 2026-04-15 20-11-50" src="https://github.com/user-attachments/assets/b280632c-c5b1-4f80-bb0e-fcd529d9a5e1" />

6.) I checked the connection by running commands like:
(whoami)
(ping google.com)
Everything was working properly.
<img width="1920" height="1200" alt="Screenshot from 2026-04-15 20-14-29" src="https://github.com/user-attachments/assets/17fd8ccc-655a-4651-a965-2d51744fa847" />
<img width="1888" height="1004" alt="Screenshot from 2026-04-15 20-15-54" src="https://github.com/user-attachments/assets/8ce7680d-dd18-4cb4-987d-f17da169a49e" />

7.) And , at the last  After  doing the testing, I removed the Elastic IP so that the instance becomes fully private again.
<img width="1920" height="1200" alt="Screenshot from 2026-04-15 20-17-04" src="https://github.com/user-attachments/assets/309f2280-4e82-48ec-b242-2a5ffb7bb898" />

RESULT-  I was able to connect to a private EC2 instance without using SSH or bastion host.











