# IAM Role with STS – Temporary S3 Access

## Project Overview
This project demonstrates how to provide temporary and secure access to AWS resources using IAM Roles and AWS Security Token Service (STS). Instead of assigning direct permissions to an IAM user, the user assumes a role that grants limited permissions for a temporary session.

This approach follows AWS security best practices by avoiding permanent permissions and enforcing least-privilege access.

## Objective
- Prevent direct permission assignment to IAM users
- Use IAM Roles to grant temporary access
- Allow an IAM user to assume a role with limited permissions
- Demonstrate secure role-based access control in AWS

## Services Used
- AWS IAM (Identity and Access Management)
- AWS STS (Security Token Service)
- Amazon S3

## Project Architecture
IAM User → Assume Role Policy → IAM Role → S3 Read-Only Access

The IAM user does not have direct access to S3.  
The user must assume the IAM role to temporarily gain read-only access to S3 resources.

## Implementation Steps

### Step 1 – Create an IAM User
- Navigate to IAM → Users
- Create a new user with AWS Management Console access
- Do not attach any permissions to the user

### Step 2 – Create an IAM Role
- Go to IAM → Roles → Create Role
- Select trusted entity type as AWS Account
- Choose "This account"
- Attach the policy **AmazonS3ReadOnlyAccess**
- Name the role `S3ReadOnlyRole`

### Step 3 – Create Assume Role Policy
- Navigate to IAM → Policies → Create policy
- Use the Visual Editor
- Service: STS
- Action: `AssumeRole`
- Resource: Select the created role `S3ReadOnlyRole`
- Name the policy `AssumeS3RolePolicy`

### Step 4 – Attach Policy to IAM User
- Go to IAM → Users
- Select the created IAM user
- Add permissions
- Attach the policy `AssumeS3RolePolicy`

### Step 5 – Testing the Setup

#### Without Role Assumption
- Login using the IAM user credentials
- Open Amazon S3 console
- Result: **Access Denied**

#### With Role Assumption
- Click **Switch Role** in the AWS console
- Enter the Account ID and role name `S3ReadOnlyRole`
- After switching roles, open Amazon S3
- Result: **Read-only access to S3**

## Expected Outcome
- IAM user cannot access S3 directly
- IAM user can assume the IAM role
- Temporary access to S3 is granted through the role
- Permissions are limited to read-only actions

## Key Learning Outcomes
- Understanding IAM Roles and temporary credentials
- Implementing least-privilege access in AWS
- Using STS for secure resource access
- Difference between direct IAM permissions and role-based access
