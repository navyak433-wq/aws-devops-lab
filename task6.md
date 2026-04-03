OBJECTIVE:-The objective of this task was to create a custom VPC with proper networking components and launch an EC2 instance inside it. After that, Nginx was installed on the instance to verify that the server is accessible through the internet.

STEPS PERFORMED:-

1.)Created a Custom VPC-
First, I logged in to the AWS Management Console and navigated to the VPC dashboard.
Then, I created a new VPC with the following configuration:
Name: my-vpc
IPv4 CIDR block: 10.0.0.0/16
<img width="1409" height="874" alt="Screenshot from 2026-04-03 20-25-13" src="https://github.com/user-attachments/assets/b085e16e-8ca5-4396-814c-2786659d0aa1" />

2.)Created Subnets-
Next, I created subnets inside the VPC:
Public Subnet (10.0.1.0/24)
The subnet was configured in the same region and availability zone.
<img width="1421" height="887" alt="Screenshot from 2026-04-03 16-30-40" src="https://github.com/user-attachments/assets/2f5bcfa5-2516-48d5-b8a0-fcd2be7b6ca9" />

3.)Created and Attached Internet Gateway-
After that, I created an Internet Gateway and attached it to the VPC to enable internet access.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-04-04" src="https://github.com/user-attachments/assets/7eb0ad46-6c0b-43bb-8955-79d4b370185d" />

4.)Created Route Table and Configured Routing-
Then, I created a route table and added a route:
Destination: 0.0.0.0/0
Target: Internet Gateway
Finally, I associated the route table with the public subnet.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-08-36" src="https://github.com/user-attachments/assets/b5c2523b-81b7-4169-9bc7-7f83171d9b78" />

5.)Created Security Group-
Next, I created a security group and allowed the following inbound rules:
SSH (port 22)
HTTP (port 80)
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-11-03" src="https://github.com/user-attachments/assets/accf8900-0fe1-494c-9c0c-f45d5fc1fd01" />

6.)Launched EC2 Instance in VPC-
Then, I launched an EC2 instance inside the created VPC and subnet:
Selected the created VPC and subnet
Attached the security group
Enabled auto-assign public IP
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-18-56" src="https://github.com/user-attachments/assets/8a3036b4-09ee-4f7c-9d03-872462ca720a" />

7.)Installed Nginx on EC2-
After connecting to the instance, I installed Nginx using the following command:
sudo yum update -y
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-25-07" src="https://github.com/user-attachments/assets/b3aed59d-a1eb-48cf-93b5-9b54ab3cb33a" />
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-22-35" src="https://github.com/user-attachments/assets/6ef07c81-e477-4b7e-a51d-f5723be1ddcf" />

8.)Tested the Web Server-
Finally, I copied the public IP of the instance and opened it in the browser.
The default Nginx page was successfully displayed.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-25-58" src="https://github.com/user-attachments/assets/87073c93-3480-43a2-b3b0-b348223924d4" />

RESULT:-Successfully created a custom VPC, configured networking components, launched an EC2 instance, and hosted a web server using Nginx.









