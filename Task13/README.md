#### Task 13: Start/Stop EC2 using Lambda + API Gateway



Definition:

In this task, I automated the start and stop operation of an EC2 instance using AWS Lambda and triggered it through API Gateway.



Objective:

The objective of this task is to understand serverless automation using Lambda and how API Gateway can be used to trigger backend actions without managing servers.



Services Used:

Amazon EC2

AWS Lambda

Amazon API Gateway

IAM Role



Step 1: Create IAM Role for Lambda



1\. Go to IAM service.

2\. Click Roles and then Create Role.

3\. Select AWS Service.

4\. Choose Lambda.

5\. Attach policy AmazonEC2FullAccess.

6\. Name the role and create it.



Step 2: Create Lambda Function



1\. Go to Lambda service.

2\. Click Create Function.

3\. Select Author from scratch.

4\. Enter function name.

5\. Choose Python runtime.

6\. Attach the IAM role created earlier.

7\. Click Create Function.



I use the following code inside Lambda:



import json

import boto3



ec2 = boto3.client('ec2')



def lambda\_handler(event, context):

&nbsp;   

&nbsp;   instance\_id = "your-ec2-instance-id"

&nbsp;   action = event.get("action")

&nbsp;   

&nbsp;   if action == "start":

&nbsp;       ec2.start\_instances(InstanceIds=\[instance\_id])

&nbsp;       return {

&nbsp;           "statusCode": 200,

&nbsp;           "body": "EC2 instance started successfully"

&nbsp;       }

&nbsp;       

&nbsp;   elif action == "stop":

&nbsp;       ec2.stop\_instances(InstanceIds=\[instance\_id])

&nbsp;       return {

&nbsp;           "statusCode": 200,

&nbsp;           "body": "EC2 instance stopped successfully"

&nbsp;       }

&nbsp;       

&nbsp;   else:

&nbsp;       return {

&nbsp;           "statusCode": 400,

&nbsp;           "body": "Invalid action. Use start or stop."

&nbsp;       }



I replace "your-ec2-instance-id" with your actual instance ID.



Step 3: Create API Gateway



1\. Go to API Gateway service.

2\. Click Create API.

3\. Choose HTTP API.

4\. Add integration and select Lambda function.

5\. Create a route (for example: /ec2).

6\. Select POST method.

7\. Deploy the API.

8\. Copy the Invoke URL.



Step 4: Test API



Use Postman or browser with request body:



{

&nbsp; "action": "start"

}



To stop:



{

&nbsp; "action": "stop"

}



API Output Example:



If successful, response will be:



EC2 instance started successfully



or



EC2 instance stopped successfully



