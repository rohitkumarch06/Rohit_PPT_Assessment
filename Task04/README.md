#### Task 4: ASG and ELB in EC2

#### 

Definition:

In this task, I configured an Auto Scaling Group with a Load Balancer to automatically scale EC2 instances based on demand and ensure high availability.



Objective:

The objective of this task is to understand scaling, load balancing, and high availability concepts in AWS.



Services Used:

Amazon EC2

Launch Template

Auto Scaling Group (ASG)

Elastic Load Balancer (Application Load Balancer)

Target Group

Security Group



Step 1: Create Launch Template



1\. Go to EC2 service.

2\. Click Launch Templates.

3\. Click Create Launch Template.

4\. Select Amazon Linux or Ubuntu AMI.

5\. Choose instance type (for example t2.micro).

6\. Select key pair.

7\. Configure security group to allow HTTP (port 80).

8\. Add user data script to install and start web server.

9\. Create Launch Template.



Example user data script:



\#!/bin/bash

sudo apt update -y

sudo apt install apache2 -y

sudo systemctl start apache2

echo "Welcome from Auto Scaling Instance" > /var/www/html/index.html



Step 2: Create Target Group



1\. Go to EC2 → Target Groups.

2\. Click Create Target Group.

3\. Select target type as Instances.

4\. Choose HTTP protocol and port 80.

5\. Select VPC.

6\. Create Target Group.



Step 3: Create Load Balancer



1\. Go to EC2 → Load Balancers.

2\. Click Create Load Balancer.

3\. Choose Application Load Balancer.

4\. Select internet-facing.

5\. Choose at least two public subnets.

6\. Attach security group allowing HTTP.

7\. Attach the Target Group created earlier.

8\. Create Load Balancer.



Step 4: Create Auto Scaling Group



1\. Go to EC2 → Auto Scaling Groups.

2\. Click Create Auto Scaling Group.

3\. Select Launch Template.

4\. Choose VPC and public subnets.

5\. Attach to existing Load Balancer.

6\. Select the Target Group.

7\. Set desired capacity (example 2).

8\. Set minimum and maximum capacity.

9\. Configure scaling policy (example: scale out if CPU > 70%).

10\. Create Auto Scaling Group.



Step 5: Testing



1\. Copy Load Balancer DNS name.

2\. Open it in browser.

3\. Website should load.

4\. Increase traffic or CPU usage to test scaling.

5\. Check if new instances are launched automatically.

