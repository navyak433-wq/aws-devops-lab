OBJECTIVE- The objective of this project is to:
Create two VPCs in two different AWS accounts
Ensure CIDR ranges do not overlap
Establish VPC Peering between them
Launch EC2 instances (public + private)
Enable SSH connection from one private instance to another.

STEPS PERFORMED:-

1.) In Account A:-
I Create VPC-1
with a CIDR Block: 10.0.0.0/16
In Account B:
I Create VPC-2
with a CIDR Block: 20.0.0.0/16
<img width="1827" height="965" alt="Screenshot from 2026-04-29 08-08-35" src="https://github.com/user-attachments/assets/78a10c89-ad5c-4fab-aff8-f091e27c826f" />
<img width="1911" height="1003" alt="Screenshot from 2026-04-29 08-09-04" src="https://github.com/user-attachments/assets/66041a28-406f-4bb9-a157-97e5dd3d8da7" />
<img width="1797" height="952" alt="Screenshot from 2026-04-29 08-10-15" src="https://github.com/user-attachments/assets/64b90a6d-4198-4f63-b9d4-829fde302312" />
<img width="1885" height="948" alt="Screenshot from 2026-04-29 08-11-23" src="https://github.com/user-attachments/assets/c6f5464e-7651-4bae-9d3e-ce85eca2f59e" />
so.Two VPCs were successfully created in different AWS accounts.
VPC-1 was created with CIDR block 10.0.0.0/16 and VPC-2 with CIDR block 20.0.0.0/16.
Both CIDR ranges are non-overlapping, which is required for VPC peering.

2.) Now,in step 2 i created Public Subnet
Subnet name: Public-Subnet
AZ: ap-southeast-2a (or any)
IPv4 CIDR: 10.0.1.0/24
<img width="1901" height="981" alt="Screenshot from 2026-04-29 08-16-37" src="https://github.com/user-attachments/assets/358d9c00-a278-46f5-8e41-82a0ae7ee76d" />
<img width="1900" height="1050" alt="Screenshot from 2026-04-29 08-17-03" src="https://github.com/user-attachments/assets/24d72497-2db9-43aa-8bbc-3778034e5928" />

now after creating public subnet,i Create Private Subnet
VPC: VPC-2
Subnet name: Private-Subnet-2
AZ: ap-southeast-2b
IPv4 CIDR: 20.0.1.0/24
<img width="1913" height="936" alt="Screenshot from 2026-04-29 08-21-07" src="https://github.com/user-attachments/assets/99ac6340-f325-4739-b169-8467333435ae" />
<img width="1919" height="832" alt="Screenshot from 2026-04-29 08-22-14" src="https://github.com/user-attachments/assets/460690e9-a3a8-42f2-a987-ea7c41f9674a" />

Private Subnet Creation in VPC-1

In this step, a private subnet was created inside VPC-1.
Subnet Name: Private-Subnet-1
VPC: VPC-1
CIDR Block: 10.0.2.0/24
Availability Zone: ap-southeast-2b
This subnet is used to host private resources such as EC2 instances that should not have direct access to the internet. It enhances security by isolating internal services from public exposure.
<img width="1918" height="1051" alt="Screenshot from 2026-04-29 08-26-26" src="https://github.com/user-attachments/assets/557af161-6f0b-44fa-8aaf-39669103307a" />
<img width="1551" height="90" alt="Screenshot from 2026-04-29 08-27-17" src="https://github.com/user-attachments/assets/3549fdf8-c00e-47cc-a635-9367aa8992cd" />

3.)n this step, an Internet Gateway was created for VPC-1.
Name: IGW-VPC1
Internet Gateway is used to connect the VPC to the internet. It allows resources inside the VPC to access the internet.
<img width="1904" height="921" alt="Screenshot from 2026-04-29 08-30-48" src="https://github.com/user-attachments/assets/ccac3883-2c40-4fde-b3e7-296bbc2a77a8" />
<img width="1873" height="838" alt="Screenshot from 2026-04-29 08-32-08" src="https://github.com/user-attachments/assets/357c134c-df15-4953-a069-40cee77bfe7d" />

4.) In this step, the Internet Gateway (IGW-VPC1) was attached to VPC-1. This attachment allows the VPC to communicate with the internet. 
After,i attached the vpc with igw it shows that it was successfully attached to vpc-1.
<img width="1919" height="732" alt="Screenshot from 2026-04-29 08-34-30" src="https://github.com/user-attachments/assets/af1e18c8-d3b6-469e-a739-e635de730efa" />
<img width="1909" height="842" alt="Screenshot from 2026-04-29 08-34-49" src="https://github.com/user-attachments/assets/aaef2a3a-d31d-44c9-ad79-2b7381bb43c6" />

5.)  Route Table and Routing
In this step, a route table named Public-RT was created in VPC-1.
A route (0.0.0.0/0) was added to connect the VPC to the Internet Gateway.
This allows the public subnet to access the internet.
The route table was then associated with the public subnet.
<img width="1919" height="776" alt="Screenshot from 2026-04-29 08-40-17" src="https://github.com/user-attachments/assets/35d51582-84b1-4411-a382-a484f74e052f" />
<img width="1914" height="813" alt="Screenshot from 2026-04-29 08-40-50" src="https://github.com/user-attachments/assets/357a57fb-8391-4f4a-b625-1e896537a716" />
<img width="1907" height="681" alt="Screenshot from 2026-04-29 08-41-23" src="https://github.com/user-attachments/assets/ed548537-a5e4-491a-8907-9bd3ca17cb4f" />

6.) In this step, the route table was connected to the public subnet.
This means that the public subnet will follow the rules of the route table.
Since the route table has internet access, the public subnet can now access the internet.
Only the public subnet was selected, and the private subnet was not selected to keep it secure.
<img width="1919" height="828" alt="Screenshot from 2026-04-29 08-46-28" src="https://github.com/user-attachments/assets/073c29fa-834e-4d3f-a7b3-14d5ba680bff" />
<img width="1904" height="957" alt="Screenshot from 2026-04-29 08-46-47" src="https://github.com/user-attachments/assets/438158cc-334a-4cc5-920b-8628641ff34e" />

7.) VPC Peering Connection Setup
In this step, a VPC peering connection was created between VPC-1 and VPC-2.
Requester VPC: VPC-1 (10.0.0.0/16)
Accepter VPC: VPC-2 (20.0.0.0/16)
Region: Same (ap-southeast-2)
The peering request was created and then accepted successfully.
This allows private communication between resources of both VPCs.
<img width="1364" height="696" alt="Screenshot from 2026-04-30 01-33-39" src="https://github.com/user-attachments/assets/8c40596f-ca66-4ae6-ae6d-f540fb5ce829" />
<img width="1339" height="667" alt="Screenshot from 2026-04-30 01-34-28" src="https://github.com/user-attachments/assets/c80d79e2-7d24-41fa-b455-bbd93c519f3c" />
<img width="1660" height="740" alt="Screenshot from 2026-04-30 01-35-32" src="https://github.com/user-attachments/assets/e09baf58-6d82-4cb4-9dc1-3a5b5d965e33" />
<img width="1352" height="731" alt="Screenshot from 2026-04-30 01-36-22" src="https://github.com/user-attachments/assets/b7a5d2bb-50f7-4357-b02d-2ec240a5c9e7" />

8.) To enable communication between the two VPCs, routes were added:
In VPC-1 route table:-
Destination: 20.0.0.0/16
Target:- VPC Peering Connection
In VPC-2 route table:
Destination: 10.0.0.0/16
Target:- VPC Peering Connection
This ensures bidirectional traffic flow between both VPCs.
<img width="1318" height="580" alt="Screenshot from 2026-04-30 01-39-37" src="https://github.com/user-attachments/assets/7d412ca6-1556-4912-a962-b1e40ba18545" />
<img width="1356" height="535" alt="Screenshot from 2026-04-30 01-40-21" src="https://github.com/user-attachments/assets/c87df600-ff50-44de-8ac3-14e82ab9ed8d" />
<img width="1322" height="451" alt="Screenshot from 2026-04-30 01-41-04" src="https://github.com/user-attachments/assets/31ee20b0-3819-4b23-814b-fc90014ed1b9" />
<img width="1361" height="533" alt="Screenshot from 2026-04-30 01-41-47" src="https://github.com/user-attachments/assets/6e5a8940-102c-4ec1-a8a8-af9f9c4ffd3a" />

9.) Instances were launched in both VPCs:
Bastion Host (Public Subnet in VPC-1)
Private EC2 (Private Subnet in VPC-1)
Private EC2 (Private Subnet in VPC-2)
<img width="1362" height="696" alt="Screenshot from 2026-04-30 01-44-51" src="https://github.com/user-attachments/assets/62595f5e-d14f-46a8-b19b-8016d7759b98" />

7.) 8.) 8.) SSH connectivity was successfully established across instances.

Step 1: Connected from local machine to Bastion Host  
Step 2: Connected from Bastion Host to Private EC2 (10.0.2.200)
This confirms that internal VPC communication is working properly.
<img width="834" height="386" alt="SSH Connectivity Screenshot" src="YOUR_SSH_SS_LINK" />
<img width="834" height="386" alt="Screenshot from 2026-04-30 01-48-43" src="https://github.com/user-attachments/assets/dc4d827d-433d-4280-9c67-fa3217d35218" />

8.) 9.) so my Cross VPC communication was verified using private IP.
Command that i used here is 
ssh ec2-user@20.0.1.161
<img width="151" height="16" alt="Screenshot from 2026-04-30 02-00-44" src="https://github.com/user-attachments/assets/775806dc-43c3-4c9b-8fa7-1ac6501c7e45" />

RESULT- VPC peering was successfully configured, and secure SSH communication between instances in both VPCs was achieved.


































