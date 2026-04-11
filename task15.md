OBJECTIVE- The objective of this task was to create an EC2 instance, configure networking, and understand how monitoring and access works in a private cloud setup.

STEPS REQUIRED:-
1.)First, I went to AWS Console and opened SNS (Simple Notification Service).
Then I created a topic which will be used to send alert messages.
After that, I created a subscription:Protocol: Email
Entered my email ID
so after this i confirmed my subscription from my email.
<img width="1393" height="707" alt="Screenshot from 2026-04-11 11-08-27" src="https://github.com/user-attachments/assets/8a860313-c094-41b5-b0b2-054bb881e019" />
<img width="1398" height="756" alt="Screenshot from 2026-04-11 11-09-52" src="https://github.com/user-attachments/assets/5945188c-9331-4815-a39d-50178d362fd3" />
<img width="1396" height="690" alt="Screenshot from 2026-04-11 11-11-36" src="https://github.com/user-attachments/assets/54324f3c-b1fa-4635-a916-cc10e5e841c9" />

2.)Next, I launched an EC2 instance which will be monitored.
<img width="1401" height="721" alt="Screenshot from 2026-04-11 11-13-08" src="https://github.com/user-attachments/assets/6eb259dc-0735-4721-84da-fc286974f4a2" />
so my instance was lanuched and it was showing running .

3.)then i have went to CloudWatch service.
Opened Alarms → Create Alarm
Selected metric: EC2 → Per Instance Metrics → CPUUtilization
Selected my EC2 instance
Set condition:
CPU > 70%
In the next step, I connected the alarm with SNS topic.
Selected existing SNS topic: CPU-Alert-Topic
This will send email when alarm triggers
In this step, I completed the alarm setup.
Gave alarm name: High-CPU-Alarm
Reviewed all configurations
Clicked on Create Alarm
<img width="1295" height="482" alt="Screenshot from 2026-04-11 11-18-34" src="https://github.com/user-attachments/assets/aeb25726-baf8-4cb1-9a18-13b8efdd29a4" />
<img width="1396" height="731" alt="Screenshot from 2026-04-11 11-19-36" src="https://github.com/user-attachments/assets/52a9691b-42d7-424f-a6c0-9d67f753d7aa" />
<img width="1399" height="664" alt="Screenshot from 2026-04-11 11-21-32" src="https://github.com/user-attachments/assets/ca42562a-9eed-485f-8fcf-f9e268655896" />

4.)I enabled detailed monitoring so that more accurate metrics can be collected, so these were the configurations i have done.
<img width="1336" height="785" alt="Screenshot from 2026-04-11 11-26-50" src="https://github.com/user-attachments/assets/d6b51b32-9561-4319-8813-e29b89aa5db8" />

RESULT-EC2 instance monitored successfully, Alarm triggered on high CPU, Email notification received









