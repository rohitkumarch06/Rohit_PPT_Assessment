#### Task 6 S3 Replication and Lifecycle Policy



Definition

In this task, I configured S3 bucket replication and lifecycle rules to manage backup and optimize storage cost automatically.



Objective

The objective of this task is to understand data backup strategy using S3 replication and cost optimization using lifecycle policies.



Services Used

Amazon S3

IAM Role

S3 Versioning

S3 Replication

Lifecycle Rules



Step 1 Create Two S3 Buckets



1\. Go to AWS Console.

2\. Open S3 service.

3\. Create first bucket (Source bucket).

4\. Create second bucket (Destination bucket).

5\. Keep both buckets in different regions (for cross-region replication).



Step 2 Enable Versioning



1\. Open Source bucket.

2\. Go to Properties.

3\. Enable Versioning.

4\. Do the same for Destination bucket.



Versioning must be enabled before configuring replication.



Step 3 Configure Replication



1\. Open Source bucket.

2\. Go to Management tab.

3\. Click Replication rules.

4\. Create replication rule.

5\. Select entire bucket or specific prefix.

6\. Choose Destination bucket.

7\. Create or select IAM role for replication.

8\. Save the rule.



Now, whenever a new object is uploaded in Source bucket, it will automatically replicate to Destination bucket.



Step 4 Configure Lifecycle Policy



1\. Open Source bucket.

2\. Go to Management tab.

3\. Click Lifecycle rules.

4\. Create lifecycle rule.

5\. Apply to all objects.

6\. Add transition action

&nbsp;  Move objects to Standard-IA or Glacier after specific days (example 30 days).

7\. Optionally set expiration rule to delete objects after certain days.

8\. Save the rule.



Step 5 Testing



1\. Upload a file to Source bucket.

2\. Verify that the file appears in Destination bucket.

3\. Check lifecycle configuration for transition or expiration settings.



Result

Objects uploaded to the source bucket are automatically replicated to the destination bucket for backup. Lifecycle rules help reduce storage cost by transitioning or deleting old objects automatically.

