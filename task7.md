OBJECTIVE:-The objective of this task was to configure path-based routing using an Application Load Balancer (ALB). Different requests were routed to different EC2 instances based on URL paths such as /images and /videos.

STEPS PERFORMED:-

1.) So, my first step was ,i created an Application Load Balancer (ALB) with:
the Scheme was  Internet-facing
Protocol was  HTTP (port 80)
Subnets was  Selected default VPC subnets
Then I attached the target groups to the load balancer.
<img width="1371" height="651" alt="Screenshot from 2026-04-30 08-24-32" src="https://github.com/user-attachments/assets/a079406c-faeb-4ad2-b490-6d416f817514" />
<img width="1355" height="710" alt="Screenshot from 2026-04-30 08-27-17" src="https://github.com/user-attachments/assets/05adf68f-9c6c-44c8-99ce-c30af438e6ee" /> (video-tg)


