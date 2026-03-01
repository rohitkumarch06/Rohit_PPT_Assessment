#### Task 7: Create EFS and Connect to Multiple Ubuntu Instances



Definition:

In this task, I created an Elastic File System (EFS) and mounted it to multiple Ubuntu EC2 instances to share storage between them.



Objective:

The objective of this task is to understand scalable and shared file systems in AWS and how EFS can be mounted across multiple EC2 instances using NFS.



Services Used:

Amazon EC2 (Ubuntu)

Amazon EFS

VPC

Security Group

NFS



Step 1: Launch EC2 Instances



1\. Go to EC2 service.

2\. Launch two Ubuntu instances in the same VPC.

3\. Ensure both instances are in the same security group or allow NFS port (2049).

4\. Note down private IP addresses.



Step 2: Create EFS



1\. Go to EFS service.

2\. Click Create File System.

3\. Select the same VPC where EC2 instances are running.

4\. Keep default settings.

5\. Create the file system.

6\. Ensure Mount Targets are created in required subnets.



Step 3: Configure Security Group



1\. Edit the EFS security group.

2\. Allow inbound rule:

&nbsp;  Type: NFS

&nbsp;  Port: 2049

&nbsp;  Source: EC2 security group or VPC CIDR.



Step 4: Install NFS Client on Ubuntu



Connect to both EC2 instances and run:



Result:

The same EFS storage was successfully mounted on multiple Ubuntu instances. Data created on one instance was accessible from the other, proving shared and scalable storage functionality.

