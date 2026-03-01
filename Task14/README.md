#### Task 14: CloudWatch Alarm (70% CPU → Auto Stop + Email)



Definition:

In this task, I created a CloudWatch alarm that monitors EC2 CPU utilization. If CPU usage goes above 70%, the instance automatically stops and an email notification is sent.



Objective:

The objective of this task is to understand AWS monitoring using CloudWatch and how automation can be configured based on metrics.



Services Used:

Amazon EC2

Amazon CloudWatch

Amazon SNS



Step 1: Create SNS Topic for Email Notification



1\. Go to AWS Console.

2\. Open SNS service.

3\. Click Create Topic.

4\. Select Standard topic.

5\. Enter topic name and create it.

6\. Create Subscription.

7\. Select Protocol as Email.

8\. Enter your email address.

9\. Confirm the subscription from your email inbox.



Step 2: Create CloudWatch Alarm



1\. Go to CloudWatch service.

2\. Click Alarms.

3\. Click Create Alarm.

4\. Select Metric.

5\. Choose EC2 → Per-Instance Metrics.

6\. Select CPUUtilization of your instance.

7\. Set condition:

&nbsp;  Threshold type: Static

&nbsp;  Whenever CPUUtilization is greater than 70%

8\. Under Actions:

&nbsp;  - Send notification to the SNS topic.

&nbsp;  - Choose EC2 action → Stop this instance.

9\. Name the alarm and create it.



Step 3: Testing

To test the alarm, increase CPU usage manually by running a stress command inside the EC2 instance. When CPU crosses 70%, the alarm state changes to In Alarm, the instance stops automatically, and an email notification is received.



Result:

When CPU utilization exceeds 70%, CloudWatch triggers the alarm, sends an email through SNS, and automatically stops the EC2 instance.

