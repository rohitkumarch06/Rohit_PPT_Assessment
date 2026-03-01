#### Task 12: Website Down Alert using Lambda (Canary) + SNS



Definition:

In this task, I configured automated website monitoring using CloudWatch Synthetics Canary and set up an SNS notification system to receive alerts if the website goes down.



Objective:

The objective of this task is to understand automated monitoring and alerting in AWS using Canary checks and SNS notifications.



Services Used:

Amazon CloudWatch Synthetics (Canary)

AWS Lambda

Amazon SNS

CloudWatch Alarms

IAM Role



Step 1: Create SNS Topic for Alerts



1\. Go to AWS Console.

2\. Open SNS service.

3\. Click Create Topic.

4\. Select Standard topic.

5\. Enter topic name and create it.

6\. Create Subscription.

7\. Choose Protocol as Email.

8\. Enter your email address.

9\. Confirm the subscription from your email inbox.



Step 2: Create Canary for Website Monitoring



1\. Go to CloudWatch service.

2\. Select Synthetics.

3\. Click Create Canary.

4\. Choose Blueprint (Heartbeat monitoring).

5\. Enter the website URL to monitor.

6\. Select runtime version.

7\. Create or select IAM role.

8\. Set schedule (for example: every 1 minute).

9\. Create Canary.



Step 3: Create CloudWatch Alarm



1\. Go to CloudWatch.

2\. Click Alarms.

3\. Click Create Alarm.

4\. Select metric from Synthetics → Canary.

5\. Choose Failed metric.

6\. Set condition: Greater than 0.

7\. In Actions, select SNS topic created earlier.

8\. Name the alarm and create it.



Step 4: Testing



To test, temporarily stop the website or enter an incorrect URL.  

When the website becomes unreachable, the Canary check fails.  

CloudWatch alarm changes to Alarm state and an email notification is sent through SNS.



Result:

The system automatically monitors website availability. If the website is down, an alert email is received without manual checking.

