2nd task-Create Snapshot and Attach Volume to EC2 Instance
so the objective of my task is
The objective of this task was to create a snapshot of an EC2 instance volume and then create a new volume from that snapshot. After that, the new volume was attached to the EC2 instance to understand how backup and recovery works in AWS.
Steps Performed during the tasks.-
First, I logged in to the AWS Management Console.

Then I opened the EC2 Dashboard.

From the left side panel, I went to Elastic Block Store → Snapshots.

I selected the snapshot of the EC2 root volume.

After that, I clicked on Actions → Create Volume from Snapshot.

While creating the volume, I selected the same Availability Zone as my EC2 instance (ap-southeast-2c) so that the volume could be attached to the instance.

Once the volume was created, I went to Elastic Block Store → Volumes.

I selected the newly created volume.

Then I clicked on Actions → Attach Volume.

In the instance dropdown, I selected my EC2 instance named snapshot-server.

I chose the device name /dev/sdf.

Finally, I clicked on Attach Volume and the volume was successfully attached to the EC2 instance.
so final conclusion is
Result

In this task, I successfully created a snapshot of the EC2 volume and then created a new volume from that snapshot. The new volume was attached to the EC2 instance and its status changed to in-use, which confirmed that the volume was successfully connected to the instance
Screenshot of snapshot creation
<img width="1920" height="1200" alt="Screenshot from 2026-03-09 11-36-03" src="https://github.com/user-attachments/assets/d921074f-f2cc-4b57-9822-b94a642811c9" />
Volume created from snapshot<img width="1920" height="1200" alt="Screenshot from 2026-03-09 11-43-34" src="https://github.com/user-attachments/assets/a3e8971f-fdbc-4a14-a120-54f1aec606b4" />
Attach volume configuration <img width="1920" height="1200" alt="Screenshot from 2026-03-09 11-40-26" src="https://github.com/user-attachments/assets/328884b7-46e0-4292-a659-2c08256b4554" />
Volume successfully attached to EC2 <img width="1920" height="1200" alt="Screenshot from 2026-03-09 11-57-40" src="https://github.com/user-attachments/assets/c3962442-b9eb-4e6e-b8dd-ed224834f90f" />

<img width="1658" height="223" alt="Screenshot from 2026-03-09 11-46-13" src="https://github.com/user-attachments/assets/299ae638-ed02-4397-834d-cfe8fce38a7c" />

