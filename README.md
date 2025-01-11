AI-Powered Document Classification with AWS

This project demonstrates a serverless AI-powered pipeline built on AWS that automates the detection of classified information in documents. It leverages natural language processing (NLP) capabilities to identify key entities like names, locations, and dates and integrates seamlessly with other AWS services to store and notify users of the results.

Features

Document Upload: Upload documents to an Amazon S3 bucket for processing.

Entity Detection: Automatically detect classified information using Amazon Comprehend.

Data Storage: Save the detected results to a DynamoDB table for tracking and analysis.

Real-Time Notifications: Get instant email alerts via Amazon SNS when classified terms are detected.

Scalability: Fully serverless and capable of handling large-scale document processing.

Architecture

S3 Bucket: Acts as the entry point for document uploads.

AWS Lambda: Processes the uploaded documents and invokes Amazon Comprehend for entity detection.

Amazon Comprehend: Analyzes the document content to identify entities.

DynamoDB: Stores the detected entities for later retrieval and analysis.

Amazon SNS: Sends email notifications when classified terms are detected.

Setup Instructions

Clone the repository to your local machine.

Deploy the CloudFormation stack included in the template.yaml file:

aws cloudformation create-stack --stack-name ai-classified-checker --template-body file://template.yaml --capabilities CAPABILITY_NAMED_IAM

Subscribe an email to the SNS topic for notifications:

aws sns subscribe --topic-arn <SNS_TOPIC_ARN> --protocol email --notification-endpoint your-email@example.com

Confirm your subscription via the email received.

Upload a document to the S3 bucket:

aws s3 cp sample-document.txt s3://<YOUR_BUCKET_NAME>/

Check DynamoDB and your email for the results.

Real-World Applications

Compliance: Automate the detection of sensitive information to maintain regulatory compliance.

Data Security: Identify and track sensitive content to reduce the risk of data leaks.

Scalable Document Processing: Handle large volumes of documents with a serverless architecture.
