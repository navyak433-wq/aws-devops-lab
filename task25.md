OBJECTIVE - To Implement Failover Routing
- Primary ALB in Region A
-Secondary ALB in Region B
- Health checks
- Automatic failover complete this task with steps and documenation

  STEPS PERFORMED :-

  1.) Launched an EC2 instance in Region A and configured a web server to serve a test webpage.
  <img width="1919" height="972" alt="Screenshot from 2026-04-26 21-59-33" src="https://github.com/user-attachments/assets/b8b1e911-1fb4-4f21-bd71-6b6d6e43685b" />
  <img width="385" height="203" alt="Screenshot from 2026-04-26 22-00-22" src="https://github.com/user-attachments/assets/ed94be86-ed19-42a5-b0af-bba1e1f79e3f" />

  2.) Created an Application Load Balancer (alb-primary) in the primary region, configured it as internet-facing, and attached it to the target group to distribute incoming traffic to the EC2 instance.
  <img width="1376" height="721" alt="Screenshot from 2026-04-26 22-12-00" src="https://github.com/user-attachments/assets/6a483bbc-e25b-4de6-a4ae-810c575e83e5" />
  <img width="1916" height="931" alt="Screenshot from 2026-04-26 22-10-20" src="https://github.com/user-attachments/assets/8051db02-99c5-4413-90d5-820876ab7ea9" />
  And aftersometime,the status become active.
  <img width="685" height="309" alt="Screenshot from 2026-04-26 22-13-15" src="https://github.com/user-attachments/assets/3528f16f-9418-4808-a809-3caeec519d36" />



 3.) After that , i Copied the DNS name of the Application Load Balancer and opened it in the browser. and it was Successfully verified that the request was routed to the EC2 instance and the webpage displayed:-
"PRIMARY SERVER"
<img width="1171" height="459" alt="Screenshot from 2026-04-26 22-36-11" src="https://github.com/user-attachments/assets/51e36e29-fd06-49af-8274-f1665b3568ff" />

4.) I also , Confirmed that the target group health checks are working correctly.
The EC2 instance responded with HTTP 200 status and remained in healthy state, ensuring proper traffic routing.
<img width="1352" height="613" alt="Screenshot from 2026-04-26 22-37-31" src="https://github.com/user-attachments/assets/a8747ae4-a167-4a18-8696-0fb2e18a47e0" />





