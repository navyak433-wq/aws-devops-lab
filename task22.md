OBJECTIVE - To monitor application health using Amazon CloudWatch, create alerts for 5xx errors, and visualize metrics using dashboards.

STEPS PERFORMED - 

1.) First I created SNS so I can get email alerts.
What I did was i Went to SNS and Created a topic that is - AlertTopic
Added my email as subscription
Confirmed it from inbox
<img width="1920" height="1200" alt="Screenshot from 2026-04-25 15-00-46" src="https://github.com/user-attachments/assets/2cdfdcf8-e972-4f10-b51a-8d2009c6434a" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-25 15-01-23" src="https://github.com/user-attachments/assets/c3b867c4-923c-4c14-aa35-70e9d59468d1" />
<img width="735" height="362" alt="Screenshot from 2026-04-25 15-03-03" src="https://github.com/user-attachments/assets/0cdcbda3-cd1d-41ec-8177-7fa9830030b3" />

2.)Now I needed to track server errors.
What I did: is that . I Opened CloudWatch Went to Logs and select Log Groups then Selected my app logs and Created a metric filter.
<img width="1920" height="1200" alt="Screenshot from 2026-04-25 15-12-11" src="https://github.com/user-attachments/assets/df99e189-f8fe-44d8-a240-d89865aee149" />
<img width="1920" height="1200" alt="Screenshot from 2026-04-25 15-18-33" src="https://github.com/user-attachments/assets/e79a359a-c4f5-47c5-9388-7a1a5468b9fa" />

3.)And the metric and alarm was created for the same.

RESULT- The task was performed and implemented.



