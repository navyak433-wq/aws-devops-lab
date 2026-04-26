OBJECTIVE:- Implement RDS Read Replica * Create MySQL RDS primary * Add read replica * Route read traffic separately from write traffic * Simulate heavy read workload.

STEPS PERFORMED :-

1.) In this step, I created a primary RDS MySQL database instance using AWS RDS service. 
I selected MySQL as the engine and configured the instance with basic settings such as username, password, and public accessibility for testing purposes. 
The database instance was successfully created and reached the available state. so the staus is showing available.
<img width="1919" height="940" alt="Screenshot from 2026-04-26 12-40-38" src="https://github.com/user-attachments/assets/e7653a1d-6dff-4d1e-896f-fb7e072718c1" />

2.)In this step, I created a read replica from the primary RDS MySQL instance. 
The read replica is used to offload read traffic from the primary database. 
AWS automatically handles data replication from the primary instance to the read replica.
so , the staus was also available.
<img width="1914" height="982" alt="Screenshot from 2026-04-26 12-52-52" src="https://github.com/user-attachments/assets/ae5280fd-76db-4d13-a4a1-70011b68ac84" />

3.)In this step, I launched an EC2 instance and used it as a client to connect to the primary database.
I installed the MySQL client and connected to the primary database using its endpoint.
After connecting:
I created a database named testdb
I created a table users
I inserted sample data into the table
I verified the data using SELECT queries
This step confirms that write operations are performed on the primary database.
<img width="1201" height="590" alt="Screenshot from 2026-04-26 13-18-45" src="https://github.com/user-attachments/assets/c2a30a0c-ea12-489a-8e80-3c4b1f9a76bf" />
<img width="1237" height="650" alt="Screenshot from 2026-04-26 13-25-13" src="https://github.com/user-attachments/assets/ae2155e7-77c9-456c-a47e-4dc350d4ea51" />

4.)4.) In this step, I connected to the read replica using its endpoint from my EC2 instance.

 after i selected the database testdb and ran a select query on the user table .
I was able to see the same data (Ansh, Rahul, Aman) which was inserted in the primary database. This shows that replication is working properly.
Then I tried to run write queries like CREATE TABLE and INSERT, but it gave an error saying the database is in read-only mode.
This confirms that:
 Read replica is successfully created
 Data is being replicated from primary to replica
 Replica only supports read operations, not write operations
 <img width="1360" height="701" alt="Screenshot from 2026-04-26 13-31-58" src="https://github.com/user-attachments/assets/52dbcd5e-f54c-44be-b8a3-437be2cd65fc" />

 5.)5.) In this step, I simulated a heavy read workload on the read replica.
I executed multiple SELECT queries continuously on the `users` table to simulate real-world read traffic.
To make it slightly heavy, I used a delay function so that queries run repeatedly and put load on the replica.
Example query used:
SELECT SLEEP(1), * FROM users;
This query runs continuously with a small delay, simulating multiple read requests.
I observed that:
All queries were executed successfully on the read replica
 Data was fetched without any issue
 No write operations were allowed (as expected)
This shows that read traffic can be offloaded to the read replica, reducing load on the primary database.
<img width="1361" height="620" alt="Screenshot from 2026-04-26 13-36-51" src="https://github.com/user-attachments/assets/ef60c96b-aec4-4c25-8f56-b5a1b1c537a0" />

6.)6.) In this task, I created an RDS MySQL primary database and a read replica.
I verified that write operations work only on the primary database, while read operations can be performed on the read replica.
I also simulated heavy read traffic using multiple SELECT queries, and the read replica handled it without any issues.
This shows that read replicas help in separating read and write traffic, reducing load on the primary database and improving performance.

RESULT:- RESULT: Successfully implemented RDS primary and read replica, and verified that read traffic can be handled separately to improve performance.



