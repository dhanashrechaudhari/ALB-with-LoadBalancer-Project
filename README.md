# Mini Project: Application Load Balancer Deployment
## Introduction
This project demonstrates the deployment and configuration of an **Application Load Balancer (ALB)** in AWS. An ALB distributes incoming HTTP/HTTPS traffic across multiple EC2 instances, enabling higher availability, fault tolerance, and scalability of web applications. Unlike the Classic Load Balancer, ALB operates at the application layer (Layer 7), allowing advanced routing features such as path-based routing, host-based routing, and SSL termination. It continuously performs health checks to ensure only healthy instances receive traffic.

## Prerequisites
AWS Account with access to EC2, ALB, and IAM services
- Multiple running EC2 instances the same VPC and region
- Security Groups configured to allow:

    - Inbound HTTP (80) / HTTPS (443) traffic
    - Inbound SSH (22) traffic (optional)
- Web Server Installed (e.g., Apache/Nginx) on each instance
- IAM Permissions to create and manage ALBs.

## Steps to Setup Application Load Balancer.
### Step 1: Launch Instances
1. Create 2 Instance of Home Page
![instance](images/1.png)

    ![instance](images/2.png)

2. Create 2 Instance of Laptop Page
![instance](images/3.png)

    ![instance](images/4.png)

3. Create 2 Instance of Mobile Page
![instance](images/5.png)

    ![instance](images/6.png)

### Step 2: Create an Application Load Balancer
1. Go to Load Balancer
![instance](images/7.png)

2. Select Application Load Balancer
![instance](images/8.png)

3. Name the Application Load Balancer
![instance](images/9.png)

4. Select all Availability Zones.
![instance](images/10.png)

5. Manage Security Group
![instance](images/11.png)

6. Create Target Group 1 (Home).
- Click on Create target group
![instance](images/12.png)
 - Select instance
![instance](images/13.png)
- Give name to target group(home-TG)
![instance](images/14.png)
- Insert health check path 
![instance](images/15.png)
- Select home instance and click on include as pending below
![instance](images/16.png)
- Click on create target group
![instance](images/17.png)

7. Create Target Group 2 (Laptop).
- Give name to target group(laptop-TG)
![instance](images/18.png)
- Insert health check path 
![instance](images/19.png)
- Click on create target group
![instance](images/20.png)

8. Create Target Group 3 (Mobile).
- Give name to target group(Mobile-TG)
![instance](images/21.png)
- Insert health check path 
![instance](images/22.png)
- Click on create target group
![instance](images/23.png)

9. Add Default action (Home-TG)
![instance](images/24.png)

10. Add Listener Rules
- Go to Rule and add Laptop Rule
![instance](images/25.png)
![instance](images/26.png)
- Go to Rule and add Mobile Rule
![instance](images/27.png)

11. Copy the DNS Command
![instance](images/28.png)

### Step 3: Testing the ALB
1. Output for Home Page 
![instance](images/29.png)

    ![instance](images/30.png)

2. Output for Laptop Page
![instance](images/31.png)

    ![instance](images/32.png)

3. Output for Mobile Page
![instance](images/33.png)

    ![instance](images/34.png)

## Summary
This mini project demonstrates the deployment and configuration of an AWS Application Load Balancer (ALB) to efficiently distribute incoming web traffic across three EC2 instances. By using a user-data script during instance launch, each server automatically runs a web server and serves unique content, allowing easy verification of traffic distribution.

