# aws-devops-lab
Repository for all AWS DevOps lab tasks and practical implementations.
AWS DevOps Lab Tasks batch 35

This repository contains AWS lab tasks and practical implementations.



 Task 1: Launch EC2 Instance and Install Nginx Web Server

### Objective
The objective of this task was to launch an EC2 instance and configure it as a web server by installing Nginx. After installation, the server was accessed through the public IP address.

 Steps Performed during

1. Logged in to the AWS Management Console.
2. Navigated to the EC2 dashboard.
3. Clicked **Launch Instance** to create a new EC2 instance.
4. Selected **Amazon Linux AMI** and chose **t3.micro** instance type.
5. Created a new key pair and downloaded the `.pem` file.
6. Configured the security group to allow **SSH (22)** and **HTTP (80)** traffic.
7. Launched the instance and waited for the state to become **Running**.
8. Connected to the instance using EC2 Instance Connect.
9. Installed Nginx using the command: sudo dnf install nginx -y
10. Started the Nginx service using:systemctl status nginx
    
11. Accessed the web server using the **Public IPv4 address** in a browser.

The Nginx web server was successfully installed and deployed on the EC2 instance. When the public IP address was opened in a browser, the default **Welcome to nginx** page was displayed, confirming that the web server was running successfully.
 Screenshot of my launched instance 
 <img width="1920" height="1200" alt="Screenshot from 2026-03-09 10-53-18" src="https://github.com/user-attachments/assets/59e7af35-ff9a-41be-bdcb-b611817b6bf3" />
screenshot of connecting my instance to ec2 instance<img width="1920" height="1200" alt="Screenshot from 2026-03-09 10-55-59" src="https://github.com/user-attachments/assets/acc2dabe-5cca-4714-8920-3c0a931690d1" />
screenshot Nginx Service Running<img width="1920" height="1200" alt="Screenshot from 2026-03-09 10-57-50" src="https://github.com/user-attachments/assets/9975644a-5896-4dc3-baa8-f2fda1807551" />
screenshot of Welcome to nginx page
<img width="1920" height="1200" alt="Screenshot from 2026-03-09 11-00-16" src="https://github.com/user-attachments/assets/ab8c13fd-a711-44b3-9b5a-cda15a5e13f2" />


