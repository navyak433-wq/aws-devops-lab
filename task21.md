OBJECTIVE - VPC Peering and Private EC2 Internet Access setup.

STEPS PERFORMED:-

1.) First, I created a custom VPC.
CIDR block: 10.0.0.0/16
Name: private-s3-vpc
<img width="1350" height="770" alt="Screenshot from 2026-04-25 16-40-59" src="https://github.com/user-attachments/assets/9dc78a6b-8731-430a-baa3-78ccf7bbb7d0" />

2.)Hub Subnet
Fill like this:
VPC ID → select hub-vpc
Subnet name → hub-subnet
Availability Zone → ap-southeast-2a 
IPv4 subnet CIDR → 10.0.1.0/24
Spoke1 Subnet
Again I  Create subnet
name -spoke1-subnet , CIDR 10.1.1.0/24
Spoke2 Subnet
VPC spoke2-vpc , Name  spoke2-subnet
CIDR 10.2.1.0/24
than we will create it.
<img width="1353" height="695" alt="Screenshot from 2026-04-25 16-54-31" src="https://github.com/user-attachments/assets/73400726-4019-4b21-83e2-7323b9b38f4e" />
<img width="1356" height="753" alt="Screenshot from 2026-04-25 16-55-12" src="https://github.com/user-attachments/assets/58bfca13-9c37-4a6d-8abe-6059a962eb89" />
<img width="1292" height="765" alt="Screenshot from 2026-04-25 16-56-00" src="https://github.com/user-attachments/assets/f0a48d08-3e91-471e-8178-ed785967cbe8" />

3.)Create VPC Peering
Name is peer-hub-spoke1
VPC (Requester) is  hub-vpc
Account is My account
Region is Same region
VPC (Accepter) is spoke1-vpc
than we will create peering connection . After creating Select the peering connection
we will  Click Actions and then  Accept request
After this we should have:
peer-hub-spoke1 is Active
peer-hub-spoke2 is Active
<img width="1344" height="762" alt="Screenshot from 2026-04-25 16-59-51" src="https://github.com/user-attachments/assets/469a0f5e-9788-4f6f-923f-4005c92d49bc" />
<img width="1339" height="731" alt="Screenshot from 2026-04-25 17-00-43" src="https://github.com/user-attachments/assets/26adf2fe-f309-4f89-83d5-a4b06568cccb" />

4.) Now , we will configure route tables 
we will open hub vpc route table that is 10.0.0.0/16 Click Edit routes - Add 2 routes
<img width="1337" height="621" alt="Screenshot from 2026-04-25 17-03-48" src="https://github.com/user-attachments/assets/b2d89fa8-2326-49cc-821a-890240d3fbd9" />

5.)Create Spoke VPCs
 Step 1- Create Spoke1 VPC
Create VPC:
Name: spoke1-vpc
CIDR: 10.1.0.0/16
and all other setting will remain same . After creating we will go to route tables and check is it created or not.
same for create Spoke2 VPC
with CIDR 10.2.0.0/16
<img width="1351" height="662" alt="Screenshot from 2026-04-25 17-10-00" src="https://github.com/user-attachments/assets/3b0c39a5-72a7-4f03-a36b-95b0e5e42325" />
<img width="1328" height="754" alt="Screenshot from 2026-04-25 17-10-41" src="https://github.com/user-attachments/assets/328dec1d-5009-44ca-93ea-7d89455723a0" />

RESULT:- n this task, I learned how to connect multiple VPCs using a hub-and-spoke architecture.
I configured VPC peering between hub and spoke VPCs and updated route tables to control traffic.
I verified that - Spoke1 and Spoke2 can communicate with the Hub
Spoke1 and Spoke2 cannot communicate with each other .








