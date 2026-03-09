# EC2 Project — Secure S3 Access Using IAM Role

## Project Summary
This project demonstrates how an EC2 instance can securely access Amazon S3 using an IAM Role instead of storing access keys. In real-world cloud environments, storing credentials inside servers or code is a security risk. AWS recommends attaching IAM roles to EC2 instances so they can receive temporary credentials automatically.

By implementing this setup, the EC2 instance can interact with S3 resources without manually configuring access keys or secret keys.

## What This Project Does
In this project, we create an S3 bucket and configure an IAM role with S3 permissions. The role is then attached to a running EC2 instance. Once attached, the EC2 instance can access S3 using AWS CLI commands without any static credentials.

This demonstrates a secure and production-ready way of allowing AWS services to communicate with each other.

## Architecture
- Amazon EC2 Instance  
- IAM Role with S3 permissions  
- Amazon S3 Bucket  
- AWS CLI inside EC2

## Steps Performed
1. Created an S3 bucket and uploaded a test file.
2. Created an IAM role for EC2 with `AmazonS3ReadOnlyAccess` permission.
3. Attached the IAM role to the running EC2 instance.
4. Connected to the EC2 instance using SSH.
5. Used AWS CLI commands to list and access S3 buckets without configuring access keys.

## Key Learning
- Difference between IAM users and IAM roles
- Secure access to AWS services without storing credentials
- Best practice for service-to-service authentication in AWS

## Outcome
The EC2 instance successfully accessed S3 resources using the IAM role, proving that AWS services can securely interact without hard-coded credentials.
