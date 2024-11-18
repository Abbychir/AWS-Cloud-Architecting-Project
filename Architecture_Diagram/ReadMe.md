# Architecture Diagram for AWS Academy Cloud Architecting Capstone Project

## Project Overview  
This repository contains the architecture diagram for the Cloud Architecting Capstone Project, demonstrating a highly available, scalable, and secure AWS solution.

## Architecture Description  
The solution utilizes the following key components:  
1. **Amazon VPC**: Provides a secure and isolated network environment.  
2. **Application Load Balancer (ALB)**: Routes traffic to multiple EC2 instances in private subnets.  
3. **Amazon RDS**: Hosts a MySQL database in a Multi-AZ setup.  
4. **Amazon S3**: Stores static assets such as images and backups.  
5. **Amazon CloudFront**: Delivers content with low latency through global edge locations.  
6. **IAM Roles and Policies**: Enforce least-privilege access control.  

## Architecture Diagram  
![AWS-Cloud-Architecting-Project/Architecture_Diagram](capstone.drawio.png)   
*(Replace with the path to your uploaded architecture image file)*

## Deployment Notes  
- **Security**: All resources are provisioned within private subnets except for the ALB and CloudFront. Security groups and NACLs ensure strict traffic control.  
- **Scalability**: Autoscaling groups handle dynamic traffic loads.  
- **Monitoring**: Amazon CloudWatch tracks logs and metrics.  

## Updates  
The architecture diagram will be updated based on feedback and iterative improvements.  

## Additional Resources  
For a detailed explanation of the architecture, refer to the [AWS Documentation](https://docs.aws.amazon.com).  
