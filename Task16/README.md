#### Task 16: RDS Database + SQL Workbench Connection \& Queries



Simple Definition:

In this task, I created a managed relational database using Amazon RDS and connected it with MySQL Workbench to run basic SQL queries.



Objective:

The main objective of this task is to understand how AWS provides managed database services and how to connect and work with them using external tools.



Services Used:

Amazon RDS (MySQL)

MySQL Workbench

VPC

Security Group



Step 1: Create RDS Database



1\. Login to AWS Console.

2\. Go to RDS service.

3\. Click on Create Database.

4\. Select Standard Create.

5\. Choose MySQL as engine type.

6\. Select Free Tier template.

7\. Enter DB Instance Identifier.

8\. Set Master Username and Password.

9\. Set Public Access to Yes.

10\. In security group, allow MySQL/Aurora (Port 3306) and select My IP as source.

11\. Click Create Database.



Step 2: Connect Using MySQL Workbench



1\. Open MySQL Workbench.

2\. Click on + to create new connection.

3\. Enter the RDS Endpoint in hostname.

4\. Set Port to 3306.

5\. Enter Master Username.

6\. Enter password when prompted.

7\. Click Test Connection and then Connect.



Step 3: Execute SQL Queries



Use the following queries in MySQL Workbench:



CREATE DATABASE studentdb;

USE studentdb;



CREATE TABLE students (

&nbsp;   id INT PRIMARY KEY AUTO\_INCREMENT,

&nbsp;   name VARCHAR(50),

&nbsp;   age INT,

&nbsp;   course VARCHAR(50)

);



INSERT INTO students (name, age, course)

VALUES ('Rohit', 21, 'BTech');



SELECT \* FROM students;

