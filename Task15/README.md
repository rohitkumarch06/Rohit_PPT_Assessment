#### Task 15: CloudFront Distribution for S3 Static Website



Simple Definition:

In this task, I used Amazon CloudFront as a Content Delivery Network (CDN) to deliver my static website stored in S3 with faster global access.



Objective:

The objective of this task is to understand how CloudFront distributes content globally using edge locations and improves website performance and latency.



Services Used:

Amazon S3

Amazon CloudFront

IAM

Bucket Policy



Step 1: Create S3 Static Website



1\. Go to AWS Console.

2\. Open S3 service.

3\. Create a new bucket.

4\. Disable Block Public Access.

5\. Upload static website files (index.html).

6\. Enable Static Website Hosting.

7\. Copy the S3 website endpoint.



Step 2: Create CloudFront Distribution



1\. Go to CloudFront service.

2\. Click Create Distribution.

3\. In Origin Domain, select the S3 bucket endpoint.

4\. Keep default settings.

5\. Set Default Root Object as index.html.

6\. Create the distribution.



Step 3: Test CloudFront URL



1\. Copy the CloudFront Domain Name.

2\. Paste in browser.

3\. Verify that the website loads successfully.



Result:

The website loads through CloudFront domain instead of direct S3 link. Content is delivered through edge locations, improving performance and reducing latency.

