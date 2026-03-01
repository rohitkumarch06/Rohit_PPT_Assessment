#### Task 8: Create IAM Users and Groups



Definition:

In this task, I created IAM users and groups to manage access and permissions in AWS. Instead of giving permissions directly to users, I assigned policies to groups and added users to those groups.



Objective:

The objective of this task is to understand access control, user management, and security policies in AWS using IAM.



Services Used:

AWS IAM

IAM Users

IAM Groups

IAM Policies



Step 1: Create IAM Group



1\. Go to AWS Console.

2\. Open IAM service.

3\. Click on User Groups.

4\. Click Create Group.

5\. Enter group name (example: Developers).

6\. Attach required policy (example: AmazonS3FullAccess or EC2ReadOnlyAccess).

7\. Create the group.



Step 2: Create IAM Users



1\. In IAM service, click Users.

2\. Click Create User.

3\. Enter username.

4\. Select access type (Console access and/or Programmatic access).

5\. Set password if console access is selected.

6\. Add user to the created group.

7\. Review and create user.



Step 3: Verify Permissions



1\. Login using IAM user credentials.

2\. Try accessing services based on attached policy.

3\. Confirm that user permissions are controlled by group policy.



Result:

Users were successfully created and added to groups. Permissions were managed through group policies, which improves security and simplifies access management.

