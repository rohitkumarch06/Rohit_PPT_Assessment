#### Task 5: Static Website Hosting in S3



Definition:

In this task, I hosted a static website using an Amazon S3 bucket without using any server.



Objective:

The objective of this task is to understand serverless hosting using S3 and how static files like HTML, CSS, and images can be served directly from a bucket.



Services Used:

Amazon S3

IAM



Step 1: Create S3 Bucket



1\. Go to AWS Console.

2\. Open S3 service.

3\. Click Create Bucket.

4\. Enter a unique bucket name.

5\. Choose region.

6\. Disable Block Public Access.

7\. Acknowledge the warning and create bucket.



Step 2: Upload Website Files



1\. Open the created bucket.

2\. Click Upload.

3\. Upload index.html and other website files.

4\. Complete upload process.



Step 3: Enable Static Website Hosting



1\. Go to Properties tab of the bucket.

2\. Scroll to Static Website Hosting.

3\. Click Edit.

4\. Enable Static Website Hosting.

5\. Enter index.html as index document.

6\. Save changes.

7\. Copy the website endpoint URL.



Step 4: Set Bucket Policy



Go to Permissions tab and add a bucket policy to allow public read access:



{

&nbsp; "Version": "2012-10-17",

&nbsp; "Statement": \[

&nbsp;   {

&nbsp;     "Effect": "Allow",

&nbsp;     "Principal": "\*",

&nbsp;     "Action": "s3:GetObject",

&nbsp;     "Resource": "arn:aws:s3:::your-bucket-name/\*"

&nbsp;   }

&nbsp; ]

}



Replace bucket-name with actual bucket name.



Step 5: Test Website



Open the website endpoint URL in browser.

The static website should load successfully.

