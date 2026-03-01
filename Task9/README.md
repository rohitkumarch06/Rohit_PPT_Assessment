#### Task 9: Access S3 from Ubuntu using IAM Roles \& Policies



Definition:

In this task, I accessed an S3 bucket securely from an Ubuntu EC2 instance using IAM Role instead of access keys.



Objective:

The objective of this task is to understand role-based access control in AWS and how IAM Roles provide secure temporary credentials to EC2 instances.



Services Used:

Amazon EC2 (Ubuntu)

Amazon S3

IAM Role and Policy

AWS CLI



Step 1: Create IAM Role



1\. Go to IAM service.

2\. Click Roles and then Create Role.

3\. Select AWS Service.

4\. Choose EC2.

5\. Attach policy AmazonS3FullAccess (or custom S3 read/write policy).

6\. Name the role and create it.



Step 2: Attach IAM Role to EC2



1\. Go to EC2 service.

2\. Select your Ubuntu instance.

3\. Click Actions.

4\. Choose Security → Modify IAM Role.

5\. Attach the IAM role created earlier.

6\. Save changes.



Step 3: Install AWS CLI in Ubuntu



Connect to EC2 using SSH and run:



sudo apt update

sudo apt install awscli -y



Check installation:



aws --version



Step 4: Test S3 Access



List S3 buckets:



aws s3 ls



Create a test file:



echo "Hello from EC2" > test.txt



Upload file to S3 bucket:



aws s3 cp test.txt s3://your-bucket-name/



Verify upload:



aws s3 ls s3://your-bucket-name/



Result:

The EC2 instance was able to access S3 without using access keys. IAM Role automatically provided temporary credentials, making the setup more secure.

