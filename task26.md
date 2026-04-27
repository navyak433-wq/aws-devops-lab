OBJECTIVE - The goal of this task was to secure a web application using AWS WAF (Web Application Firewall) by attaching it to an Application Load Balancer (ALB) and testing the setup using an EC2 instance.

STEPS PERFORMED :-

1.) I selected my Application Load Balancer named my-alb
This ALB will receive traffic and forward it to backend EC2.
<img width="1359" height="736" alt="Screenshot from 2026-04-27 15-06-22" src="https://github.com/user-attachments/assets/e6f1cb78-da1a-4e00-9a2c-b8ba3ff2026d" />
and after sometime the stauts was active.
<img width="930" height="328" alt="Screenshot from 2026-04-27 15-08-24" src="https://github.com/user-attachments/assets/0a875c18-41b2-4d88-8c5b-394a7881b980" />

2.)Created a Web ACL named my-waf-acl
Selected option: Build your own pack
Attached it to the ALB
<img width="1354" height="767" alt="Screenshot from 2026-04-27 15-09-19" src="https://github.com/user-attachments/assets/c25a4a2c-6b07-4375-aa7e-d3fd736623a9" />

3.) SQL Injection Rule
Used AWS Managed Rule: AWSManagedRulesSQLiRuleSet
Protects against SQL injection attacks
<img width="1374" height="713" alt="Screenshot from 2026-04-27 15-10-37" src="https://github.com/user-attachments/assets/8be1e2c9-fd6b-4c92-b62b-db5c0ed94600" />
<img width="1363" height="689" alt="Screenshot from 2026-04-27 15-11-31" src="https://github.com/user-attachments/assets/f68e8ecb-5d15-4aac-8d75-810c7a7aa3d6" />

4.)Created custom rule: rate-limit-rule
Limit: 100 requests in 5 minutes
Action: Block
<img width="1352" height="726" alt="Screenshot from 2026-04-27 15-13-02" src="https://github.com/user-attachments/assets/5cf180af-ede3-4e63-a5f5-633ebc4485c3" />
<img width="1378" height="737" alt="Screenshot from 2026-04-27 15-13-57" src="https://github.com/user-attachments/assets/8b1e4b99-ad22-45ee-bb5f-184724ef3b68" />

5.)Created rule: geo-block-rule
Blocked traffic from China .
It basically helps to estrict traffic from unwanted countries.
<img width="1355" height="683" alt="Screenshot from 2026-04-27 15-16-29" src="https://github.com/user-attachments/assets/9343487e-7326-4f7d-817b-93515ed5139b" />
<img width="1359" height="722" alt="Screenshot from 2026-04-27 15-17-17" src="https://github.com/user-attachments/assets/353c40ca-21d8-4c41-b36d-b564f52871c7" />

6.) All three rules were added .
After adding all rules, clicked Create protection pack
WAF got attached to ALB successfully.
<img width="1360" height="716" alt="Screenshot from 2026-04-27 15-18-03" src="https://github.com/user-attachments/assets/6e4c1acd-8a49-4082-8cd1-9097580282a5" />
<img width="1354" height="586" alt="Screenshot from 2026-04-27 15-20-41" src="https://github.com/user-attachments/assets/f9965766-2575-4c21-924c-3fec1b58bfde" />

7.) Launched EC2 instance (my curl-instance)
Installed Apache server:
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
Created test webpage:
echo "Hello from backend" | sudo tee /var/www/html/index.html
<img width="1368" height="588" alt="Screenshot from 2026-04-27 15-26-12" src="https://github.com/user-attachments/assets/bbff44a7-dee7-4774-bfae-604e0fc1fdac" />

8.) Configure Security Group
Allowed:
HTTP (80)
HTTPS (443)
SSH (22)
<img width="1341" height="556" alt="Screenshot from 2026-04-27 15-29-05" src="https://github.com/user-attachments/assets/3a585857-c41e-43c7-97e4-60c2ccbb76e9" />

9.) Added EC2 instance to target group (app-asg-1)
Linked target group with ALB
<img width="1353" height="453" alt="Screenshot from 2026-04-27 15-30-21" src="https://github.com/user-attachments/assets/2f358d23-2192-4258-a683-038b0c4364a4" />

10.) Test using curl:-
so this was the output
curl http://my-alb-262103139.ap-southeast-2.elb.amazonaws.com
<img width="918" height="43" alt="Screenshot from 2026-04-26 20-41-06" src="https://github.com/user-attachments/assets/c467de27-97b0-4baa-a155-d116f7ef50d3" />
This shows:
ALB is working
EC2 is responding
WAF is attached successfully

RESULT:-The AWS WAF was successfully configured and integrated with the Application Load Balancer and EC2 instance, and the setup was verified using curl with a successful backend response.













