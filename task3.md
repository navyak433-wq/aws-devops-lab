objective of my task:-
The main objective of this task was to launch an EC2 instance and install a web server (Nginx) on it. After that, I created a simple web page to check if the server is working properly. Then I created an AMI from that instance and used it to make a launch template. Finally, I configured an Auto Scaling Group so that instances can be managed automatically
steps performed during my tasks:-
First, I logged in to the AWS Management Console.
Then I went to the EC2 dashboard and clicked on Launch Instance.
I selected Amazon Linux AMI and chose the instance type as t3.micro.
After that, I created a new key pair and downloaded it.
In the network settings, I allowed HTTP (port 80) so that I can access the web server from the browser.
Then I launched the instance and waited for it to run.
Once the instance was running, I connected to it using EC2 Instance Connect.
After connecting, I installed Nginx using commands and started the service.(sudo yum install nginx -y)
Then I checked the Nginx status to make sure it is running properly.(sudo systemctl start nginx)
After that, I edited the default HTML file and added my own custom content.
I copied the public IP of the instance and opened it in the browser to verify the web page.
Once everything was working fine, I created an AMI (image) from that EC2 instance.
After the image was available, I used it to create a launch template.
Then I created an Auto Scaling Group using that launch template.
I configured the desired, minimum, and maximum number of instances.
Finally, I verified that multiple instances were launched automatically.

Screenshot1: EC2 instances running:-

<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-54-42" src="https://github.com/user-attachments/assets/1d7e906c-75c5-4573-87fe-13ef119bfee8" />
<img width="1403" height="792" alt="Screenshot from 2026-03-29 15-35-31" src="https://github.com/user-attachments/assets/ad3e0e1f-b735-4cb0-93bb-96e29198c088" />

screenshot2: nginx-status.png:-

<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-32-04" src="https://github.com/user-attachments/assets/c6aa2e1d-3671-4084-8e22-c2f128afd8e8" />

screenshot3:-web-page.png
<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-37-36" src="https://github.com/user-attachments/assets/23bc1b27-38b9-44cd-90ec-f9eeada4c854" />

screenshot4:-ami-created.png

<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-52-39" src="https://github.com/user-attachments/assets/f84ca7ba-bfbb-431e-b200-894e7423ba27" />

screenshot5:-launch-template.png

<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-46-16" src="https://github.com/user-attachments/assets/bf6c233c-6976-4653-bbf5-c164a8ed8adf" />

screenshot6:-asg-created.png

<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-52-39" src="https://github.com/user-attachments/assets/3c3f76da-13ec-44b2-9bd5-91d5c72ff031" />

screenshot 7:-multiple-instances.png
<img width="1920" height="1200" alt="Screenshot from 2026-03-29 14-54-42" src="https://github.com/user-attachments/assets/a3eff7d3-e74b-41af-b26b-e493cd1a214d" />

Result:

In this task, I learned how to launch an EC2 instance and set up a web server using Nginx. I also created my own web page and checked it using the public IP. Then I created an AMI and used it to make a launch template and Auto Scaling Group. In the end, I saw that multiple instances were created automatically, so the setup worked successfully.
