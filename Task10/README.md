#### Task 10: VPC 3-Tier Architecture



Definition:

In this task, I designed a 3-tier architecture inside a custom VPC using public and private subnets. The architecture separates web, application, and database layers for better security and scalability.



Objective:

The objective of this task is to understand AWS networking concepts such as VPC, subnets, route tables, Internet Gateway (IGW), NAT Gateway, Network ACL (NACL), and SSH tunneling.



Services Used:

Amazon VPC

EC2 Instances

Internet Gateway

NAT Gateway

Route Tables

Network ACL

Security Groups



Architecture Overview:



Tier 1 (Web Tier - Public Subnet)

\- EC2 instance hosted in public subnet

\- Connected to Internet Gateway

\- Accessible from internet



Tier 2 (Application Tier - Private Subnet)

\- EC2 instance in private subnet

\- No direct internet access

\- Internet access only through NAT Gateway



Tier 3 (Database Tier - Private Subnet)

\- Database instance in private subnet

\- No direct internet access

\- Accessible only from Application tier



Step 1: Create VPC



1\. Go to VPC service.

2\. Click Create VPC.

3\. Provide VPC name and CIDR block (example: 10.0.0.0/16).

4\. Create VPC.



Step 2: Create Subnets



1\. Create one Public Subnet (example: 10.0.1.0/24).

2\. Create two Private Subnets (example: 10.0.2.0/24 and 10.0.3.0/24).

3\. Enable Auto-assign Public IP only for Public Subnet.



Step 3: Create and Attach Internet Gateway



1\. Create Internet Gateway.

2\. Attach it to the VPC.

3\. Create a route table for Public Subnet.

4\. Add route:

&nbsp;  Destination: 0.0.0.0/0

&nbsp;  Target: Internet Gateway.

5\. Associate Public Subnet with this route table.



Step 4: Create NAT Gateway



1\. Allocate Elastic IP.

2\. Create NAT Gateway in Public Subnet.

3\. Create Route Table for Private Subnets.

4\. Add route:

&nbsp;  Destination: 0.0.0.0/0

&nbsp;  Target: NAT Gateway.

5\. Associate Private Subnets with this route table.



Step 5: Launch EC2 Instances



1\. Launch Web Server in Public Subnet.

2\. Launch Application Server in Private Subnet.

3\. Launch Database Server in Private Subnet.

4\. Configure Security Groups properly.



Step 6: SSH Tunneling



1\. Connect to Web Server using public IP.

2\. From Web Server, SSH into private Application Server using private IP.

3\. From Application Server, connect to Database Server.



Result:

The Web tier is publicly accessible.

The Application and Database tiers are secured in private subnets.

Private instances access the internet only through NAT Gateway.

SSH tunneling allows secure internal communication.

