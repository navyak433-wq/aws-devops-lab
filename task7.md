OBJECTIVE:-The objective of this task was to configure path-based routing using an Application Load Balancer (ALB). Different requests were routed to different EC2 instances based on URL paths such as /images and /videos.

STEPS PERFORMED:-

1.)Created Target Groups

First, I created two target groups:
One for handling image requests
One for handling video requests
Both target groups were configured with HTTP protocol on port 80.
<img width="1402" height="809" alt="Screenshot from 2026-04-03 23-04-55" src="https://github.com/user-attachments/assets/cf18a9b4-689c-4425-9262-ddd0bf39a77a" />

