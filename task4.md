OBJECTIVE- The objective of this task was to install and run Jenkins on an AWS EC2 instance and access it through a web browser.
STEPS PERFORMED-
1.) Launching EC2 Instance
First, I launched a new EC2 instance from AWS.
I selected Amazon Linux as the AMI and t3.micro as the instance type.
In the security group, I allowed ports 22 (SSH), 80 (HTTP), and 8080 (Custom TCP) for Jenkins.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 13-17-32" src="https://github.com/user-attachments/assets/691c403d-72d5-45bb-9b6d-c665ba81f9c0" />

2.) Connecting to EC2 Instance
Then, I connected to the instance using EC2 Instance Connect and opened the terminal.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 15-55-09" src="https://github.com/user-attachments/assets/859faaa6-773c-4fb0-b48a-e18b8b1902af" />

3.) Installing Java and Jenkins
After that, I installed Java and Jenkins by running all the required commands together in the terminal.
sudo dnf update -y , sudo dnf install java-17-amazon-corretto -y , sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo , sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key , sudo dnf install jenkins -y these were the commands that i used.
Than i have Starting Jenkins Service
Then, I started the Jenkins service and enabled it by using some commands
sudo systemctl start jenkins , sudo systemctl enable jenkins , sudo systemctl status jenkins
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 16-03-09" src="https://github.com/user-attachments/assets/dbf733b7-c1df-437c-903c-46599101f52f" />

4.) Than Accessing Jenkins in Browser
After that, I copied the public IP of the instance and opened it in the browser using port 8080.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 16-04-39" src="https://github.com/user-attachments/assets/6d3b352e-dfa8-4642-9899-0b38901018fb" />
Then, I retrieved the initial admin password using the terminal.I copied the password and entered it in the browser.

5.)nstalling Plugins
Next, I selected "Install suggested plugins" and waited for the installation to complete.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 16-06-55" src="https://github.com/user-attachments/assets/67656ef0-d61a-47ee-b939-1cd4c82a3cfa" />

6.) Creating Admin User
After that, I created an admin user by entering username, password, and email.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 16-10-15" src="https://github.com/user-attachments/assets/21c2328f-4b10-4cc2-8dc4-662db43c4448" />

7.)Jenkins Setup Completed
Finally, Jenkins displayed "Jenkins is ready", and the dashboard opened successfully.
<img width="1920" height="1200" alt="Screenshot from 2026-03-31 16-13-07" src="https://github.com/user-attachments/assets/d6354e50-23e2-4470-8401-4c567b7142d0" />

RESULT-Jenkins was successfully installed and configured on an AWS EC2 instance and accessed through a web browser.


