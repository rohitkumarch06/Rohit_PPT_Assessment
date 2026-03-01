#### Task 3: Attach EBS Volume from Different AZ using Snapshot



Definition:

In this task, I created a snapshot of an EBS volume and restored it in a different Availability Zone to attach it to another EC2 instance.



Objective:

The objective of this task is to understand how EBS snapshots work and how storage can be moved across Availability Zones using snapshots.



Services Used:

Amazon EC2

Amazon EBS

EBS Snapshot

Availability Zones



Step 1: Create EBS Volume and Attach to EC2



1\. Go to EC2 service.

2\. Launch an EC2 instance in Availability Zone A.

3\. Go to Volumes section.

4\. Create a new EBS volume in the same AZ.

5\. Attach the volume to the EC2 instance.

6\. Connect to instance and format/mount the volume if required.

7\. Create some test data inside the volume.



Step 2: Create Snapshot



1\. Go to EC2 → Volumes.

2\. Select the attached EBS volume.

3\. Click Actions → Create Snapshot.

4\. Enter description and create snapshot.

5\. Wait until snapshot status becomes Completed.



Step 3: Create Volume in Different AZ



1\. Go to EC2 → Snapshots.

2\. Select the created snapshot.

3\. Click Actions → Create Volume.

4\. Choose a different Availability Zone (for example AZ B).

5\. Create the volume.



Step 4: Attach New Volume to EC2 in Different AZ



1\. Launch a new EC2 instance in AZ B.

2\. Go to Volumes.

3\. Select the new volume created from snapshot.

4\. Click Attach Volume.

5\. Choose the new EC2 instance.

6\. Connect to instance and mount the volume.



Step 5: Verify Data



Check if the previously created data is available in the new instance after mounting the volume.



Result:

Using EBS snapshot, I successfully copied data from one Availability Zone to another. Since EBS volumes cannot be directly attached across different AZs, snapshots are used to recreate volumes in another zone.

