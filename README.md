AWS Academy Cloud Architecting – Capstone Project

This project provides a scalable and secure architecture for hosting a PHP-based web application with a MySQL database. The application is designed to serve global development statistics to social science researchers. This solution uses AWS services such as EC2, RDS, ALB, Auto Scaling, and Secrets Manager to ensure high availability, security, and scalability.

 Architecture Overview

The architecture consists of the following components:

1. Amazon RDS (MySQL Database) 
   - The MySQL database is hosted on Amazon RDS and is located in a private subnet. The application uses Secrets Manager to securely store and retrieve database credentials.

2. Application Load Balancer (ALB)
   - The ALB is deployed in public subnets and distributes incoming traffic across multiple EC2 instances running the PHP application. The ALB ensures high availability by routing traffic to healthy instances.

3. Amazon EC2 Instances (Web Servers)
   - EC2 instances running Amazon Linux 2023 host the PHP application. The instances are placed in private subnets for security and scalability. The Auto Scaling Group ensures that the application can scale based on incoming traffic.

4. Auto Scaling
   - Auto Scaling ensures that the application scales dynamically based on load, using a launch template to configure the EC2 instances.

5. Secrets Manager
   - AWS Secrets Manager is used to store database credentials securely, ensuring that they are not hardcoded in the application code.


 Key Design Decisions

1. High Availability
   - The Application Load Balancer and EC2 instances are deployed in multiple Availability Zones for fault tolerance. The RDS MySQL database is also deployed with Multi-AZ support for high availability.

2. Security
   - The EC2 instances are placed in private subnets to prevent direct access from the internet. Only the ALB is accessible publicly.
   - Database credentials are stored in Secrets Manager, ensuring secure access to the MySQL database.

3. Scalability
   - The Auto Scaling Group ensures that the number of EC2 instances can scale up or down based on traffic. The Application Load Balancer balances traffic to ensure smooth performance even with fluctuating loads.

4. Cost Management
   - The EC2 instances are sized appropriately (t2.micro) to meet the requirements without incurring unnecessary costs. The use of RDS with a small db.t3.micro instance ensures cost-effective database hosting.

 Project Steps

Step 1: Creating Amazon RDS MySQL Database
- Create an RDS instance in a private subnet using the db.t3.micro instance type.
- Store database credentials in Secrets Manager.

Step 2: Configuring the Application Load Balancer (ALB)
- Deploy the ALB in public subnets and configure it to distribute traffic to EC2 instances in private subnets.

 Step 3: Launch EC2 Instances in an Auto Scaling Group
- Use the provided EC2 launch template and Auto Scaling group to deploy the PHP application.
- Configure the Auto Scaling policy to adjust based on traffic.

 Step 4: Data Import into RDS MySQL Database
- Use the provided SQL dump file to import data into the MySQL database.

 Step 5: Test the Application
- Test the application by accessing it via the ALB DNS name in a browser.
- Verify that the PHP application retrieves data from the RDS database corr





