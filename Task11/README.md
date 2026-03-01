#### Task 11: S3 Upload Email Notification (Lambda + SNS)



Definition:

In this task, I configured an automatic email notification system that sends an alert whenever a file is uploaded to an S3 bucket using Lambda and SNS.



Objective:

The objective of this task is to understand event-driven architecture in AWS where one service triggers another automatically.



Services Used:

Amazon S3

AWS Lambda

Amazon SNS

IAM Role



Step 1: Create SNS Topic



1\. Go to AWS Console.

2\. Open SNS service.

3\. Click Create Topic.

4\. Select Standard topic.

5\. Enter topic name and create it.

6\. Create Subscription.

7\. Select Protocol as Email.

8\. Enter my email address.

9\. Confirm the subscription from my email inbox.



Step 2: Create IAM Role for Lambda



1\. Go to IAM service.

2\. Click Roles and then Create Role.

3\. Select AWS Service.

4\. Choose Lambda.

5\. Attach policy AmazonS3FullAccess and AmazonSNSFullAccess.

6\. Name the role and create it.



Step 3: Create Lambda Function



1\. Go to Lambda service.

2\. Click Create Function.

3\. Select Author from scratch.

4\. Choose Python runtime.

5\. Attach the IAM role created earlier.

6\. Click Create Function.



Use the following code inside Lambda:



import json

import boto3



sns = boto3.client('sns')



def lambda\_handler(event, context):

&nbsp;   

&nbsp;   topic\_arn = "your-sns-topic-arn"

&nbsp;   

&nbsp;   bucket\_name = event\['Records']\[0]\['s3']\['bucket']\['name']

&nbsp;   file\_name = event\['Records']\[0]\['s3']\['object']\['key']

&nbsp;   

&nbsp;   message = f"New file uploaded to S3 bucket.\\nBucket: {bucket\_name}\\nFile: {file\_name}"

&nbsp;   

&nbsp;   sns.publish(

&nbsp;       TopicArn=topic\_arn,

&nbsp;       Message=message,

&nbsp;       Subject="S3 Upload Notification"

&nbsp;   )

&nbsp;   

&nbsp;   return {

&nbsp;       'statusCode': 200,

&nbsp;       'body': 'Notification sent successfully'

&nbsp;   }





Step 4: Configure S3 Trigger



1\. Go to S3 service.

2\. Create a bucket (if not already created).

3\. Open the bucket.

4\. Go to Properties.

5\. Under Event Notifications, click Create Event Notification.

6\. Select event type as All object create events.

7\. Select Lambda function as destination.

8\. Save changes.



Step 5: Testing



Upload any file to the S3 bucket.

Once the file is uploaded, Lambda gets triggered automatically.

SNS sends an email notification with bucket name and file name.

