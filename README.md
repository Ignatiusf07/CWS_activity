# Serverless File Processing & Monitoring System using AWS

A fully serverless, event-driven cloud solution that automatically processes file uploads, logs events, and sends real-time notifications using core AWS services.
This project demonstrates practical implementation of AWS Cloud concepts such as S3 event triggers, Lambda serverless compute, CloudWatch monitoring, and SNS alerting.

🚀 Project Overview

This system monitors an Amazon S3 bucket for new file uploads and triggers an AWS Lambda function to process events.
Lambda logs details to Amazon CloudWatch, and sends email alerts via Amazon SNS.
The solution is fully serverless—no servers to manage, scale, or secure manually.

This project is based on the architecture and steps documented in the report 

Serverless File Processing & Mo…

.

🧩 Architecture Workflow

A user uploads a file into the uploads/ folder inside S3.

S3 publishes an event to AWS Lambda.

Lambda extracts metadata, logs the event, and triggers an SNS notification.

CloudWatch stores logs and provides monitoring dashboards.

SNS sends real-time email alerts to subscribed users.

(Optional) CloudWatch Alarms can monitor errors and trigger alerts.

Diagram described in the report:
The workflow figure on page 2–3 illustrates the S3 → Lambda → CloudWatch → SNS pipeline clearly. 

Serverless File Processing & Mo…

🏗️ AWS Services Used

Amazon S3 – File storage & event source

AWS Lambda – Serverless compute for processing events

Amazon SNS – Email notifications for new uploads

Amazon CloudWatch – Logs, dashboards & monitoring

AWS IAM – Secure role-based access control

Service list sourced from page 2 of the report. 

Serverless File Processing & Mo…

📦 Project Folder Structure (S3)

As configured during implementation:

serverless-file-bucket-yourname/
│
├── uploads/
│     └── (incoming files)
│
└── processed/
      └── (optional processed files)


(Structure shown in screenshots on page 3 of the report.) 

Serverless File Processing & Mo…

🛠️ Implementation Steps
1️⃣ Create S3 Bucket

Create bucket

Enable block-all-public access

Create folders: uploads/ and processed/
(Screenshots available on page 8–9.) 

Serverless File Processing & Mo…

2️⃣ Configure IAM

Create IAM role for Lambda

Attach required policies:

AmazonS3FullAccess

CloudWatchLogsFullAccess
Set Up CloudWatch Monitoring

View Lambda logs

Create dashboard widgets:

Lambda invocations

Lambda errors

S3 metrics

SNS delivery metrics

(Optional) Create CloudWatch alarm for Lambda errors
(Steps and visual examples on page 13.) 

Serverless File Processing & Mo…

5️⃣ Configure SNS Notifications

Create SNS Topic

Add email subscription(s)

Confirm subscription via email
(Screenshots on page 14–15.) 

Serverless File Processing & Mo…

📬 Result

Once deployed:

✔️ S3 automatically detects file uploads
✔️ Lambda executes instantly
✔️ CloudWatch logs the event
✔️ SNS sends an email such as:

“New file uploaded: uploads/test3.txt”

Confirmed in screenshots on page 16. 

Serverless File Processing & Mo…

🏁 Conclusion

This project demonstrates how AWS serverless architecture can automate workflows with minimal setup, zero server maintenance, and high scalability.
It aligns with AWS best practices in event-driven design, monitoring, and secure IAM-based access control.
(Conclusion sourced from page 16.) 

Serverless File Processing & Mo…

📄 How to Use / Deploy

Clone repository

Copy the Lambda function code into AWS Lambda

Replace SNS Topic ARN in code

Create S3 bucket with required structure

Upload any file to uploads/

Receive logs + email notifications

AmazonSNSFullAccess

Assign role to Lambda
