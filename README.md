# 360-Customer-View

Introduction

In modern organizations, understanding customers from multiple perspectives is vital for effective decision-making. Businesses analyze dimensions such as customer loyalty (e.g., years of history, frequency of interaction) and demographics (e.g., stage of life, income). These dimensions collectively provide a 360-degree customer view, offering insights into various aspects simultaneously.

However, achieving this comprehensive view presents challenges like:

Data Fragmentation: Data scattered across multiple source systems.
Data Governance: Ensuring compliance and consistency.
Data Growth: Managing ever-expanding datasets.
Data Change: Adapting to dynamic data structures and content.
This Project focuses on creating a Customer 360 View for a hypothetical company by addressing these challenges with AWS services.

Architecture Overview

Tools and Frameworks
Data Extraction:

AWS Glue: Connects relational databases to Amazon S3 via Glue Connectors and Jobs.
Persistent Data Layer:

Amazon S3 Buckets for the Raw, Stage, and Analytics data layers, forming the backbone of the data lake strategy.
Data Processing:

AWS Step Functions: Orchestrates workflows.
AWS Lambda: Executes serverless functions.
Amazon EMR: Utilizes Spark and Hive for large-scale transformations.
AWS Glue: Runs Spark and Python-based ETL jobs.
Amazon Athena: Enables SQL querying on S3-based data.
Data Consumption:

Amazon Athena Console/API: Query data for insights.
Amazon DynamoDB Console/API: Manage key-value data for rapid access.
Data Sources and Formats
Domain	Data Source	Format	Key Columns
Customer Info	CRM (API)	JSON	client_id, age, marital_status
Transactions	Mainframe Relational DB	Relational DB	trans_id, amount, balance
Credit Card	Card Origination System	Text	card_id, issued_datetime
Account	Account Origination System	Text	account_id, branch_ID
General Banking	Dispositions Database	Text	disp_id, client_id
Web Analytics	Google Analytics	JSON (Nested Fields)	client_id, visitNumber
Shopping History	Retail Sales Orders	CSV	client_id, sales, quantity
AWS Infrastructure
Amazon S3 Buckets:

RawDataS3Bucket, StageDataS3Bucket, AnalyticsDataS3Bucket, LogDataS3Bucket.
RDS Instance:

Aurora PostgreSQL for simulating transaction data.

AWS Lambda Functions:

Simulate external integrations like CRM data, mainframe extracts, and Google Analytics.
Amazon EMR Cluster:

For advanced processing of Spark and Hive workloads.

EventBridge Rules:

Schedule Lambda executions for data ingestion.

IAM Roles:

Defined for Glue and Lambda functions to manage permissions securely.

Summary

In this project, we use AWS Glue, Amazon S3, Amazon EMR, and other AWS tools to integrate data from various sources. By solving real-world challenges, you'll build a Customer 360 View, gaining hands-on experience with scalable data pipelines and AWS analytics solutions.
