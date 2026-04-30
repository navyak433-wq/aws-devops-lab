OBJECTIVE:-The objective of this task was to configure path-based routing using an Application Load Balancer (ALB). Different requests were routed to different EC2 instances based on URL paths such as /images and /videos.

STEPS PERFORMED:-

1.) So, my first step was ,i created an Application Load Balancer (ALB) with:
the Scheme was  Internet-facing
Protocol was  HTTP (port 80)
Subnets was  Selected default VPC subnets
Then I attached the target groups to the load balancer.
<img width="1371" height="651" alt="Screenshot from 2026-04-30 08-24-32" src="https://github.com/user-attachments/assets/a079406c-faeb-4ad2-b490-6d416f817514" />
<img width="1355" height="710" alt="Screenshot from 2026-04-30 08-27-17" src="https://github.com/user-attachments/assets/05adf68f-9c6c-44c8-99ce-c30af438e6ee" /> (video-tg)
Next, I registered the EC2 instances with their respective target groups.
<img width="1348" height="693" alt="Screenshot from 2026-04-30 11-37-28" src="https://github.com/user-attachments/assets/b7a59fc0-1f99-4f5d-a29c-4b0f2cb41874" />
Next we have launched ec2 instance , 
<img width="1321" height="736" alt="Screenshot from 2026-04-30 11-39-15" src="https://github.com/user-attachments/assets/e4e564e8-f05f-4828-86ef-e869178523ab" />
<img width="1352" height="656" alt="Screenshot from 2026-04-30 11-40-32" src="https://github.com/user-attachments/assets/847bed2d-74e6-42ed-8e14-76f36161e0f9" />
Now i haven taken the public ip of my instance and will connect my instance with ec2 and will start install nginx
<img width="1295" height="623" alt="Screenshot from 2026-04-30 11-43-40" src="https://github.com/user-attachments/assets/a42c2f4c-7d36-4825-b5ca-87ff64b487b3" />
<img width="1333" height="719" alt="Screenshot from 2026-04-30 11-45-00" src="https://github.com/user-attachments/assets/209a187d-6689-46fc-8c96-0c7e83d189f3" />
after that my image page was open through alb.
<img width="638" height="324" alt="Screenshot from 2026-04-30 11-49-52" src="https://github.com/user-attachments/assets/4e32cbc5-926c-48dd-95e9-3c400557eb1f" />
<img width="1252" height="625" alt="Screenshot from 2026-04-30 11-57-23" src="https://github.com/user-attachments/assets/a16fbc5c-93a2-4158-84b6-14a77a76252f" />
Finally i have mapped with router 53.

RESULT- hence,i have implemented this task to configure path-based routing using an Application Load Balancer (ALB). Different requests were routed to different EC2 instances based on URL paths such as /images and /videos.










