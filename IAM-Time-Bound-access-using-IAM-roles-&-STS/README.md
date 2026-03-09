# IAM Project – Temporary Access Using IAM Role and AWS STS

## 📌 Project Summary
This project demonstrates how to provide temporary and secure access to AWS resources using IAM Roles and AWS Security Token Service (STS).

Instead of giving permanent permissions to users, the user assumes a role that grants limited access for a specific duration. This approach follows security best practices used in real-world organizations.

In this project, an IAM user initially has no permissions. The user can only access EC2 resources after switching to an IAM role that provides temporary read-only access.

---

## 🎯 Project Objective
The objective of this project is to demonstrate how AWS IAM roles and STS can be used to provide temporary access without assigning permanent permissions to users.

---

## 🛠 AWS Services Used
- AWS IAM (Identity and Access Management)
- AWS STS (Security Token Service)
- Amazon EC2

---

## 🏗 Project Architecture

IAM User (No Permissions)  
↓  
Assume IAM Role using STS  
↓  
Temporary EC2 Read-Only Access  
↓  
Access Expires Automatically

---

## ⚙️ Implementation Steps

### Step 1 – Create IAM User
- Navigate to **IAM → Users**
- Create a user named `limited_user`
- Enable AWS Management Console access
- Do not attach any permissions

---

### Step 2 – Create IAM Role
- Navigate to **IAM → Roles → Create Role**
- Trusted entity type: **AWS Account**
- Select **This Account**
- Role name: `TemporaryEC2ReadRole`

---

### Step 3 – Attach Permission to Role
Attach the AWS managed policy:

AmazonEC2ReadOnlyAccess

This policy allows the role to view EC2 resources but not modify them.

---

### Step 4 – Configure Trust Relationship
Modify the trust relationship so that the IAM user can assume the role.

This allows the IAM user to perform the **sts:AssumeRole** action.

---

### Step 5 – Set Session Duration
Set the maximum session duration to **1 hour** in the role settings.  
This ensures that the access provided by the role is temporary.

---

### Step 6 – Allow User to Assume Role
Add an inline policy to the IAM user allowing:

sts:AssumeRole

for the role **TemporaryEC2ReadRole**.

---

### Step 7 – Testing
1. Login using `limited_user`
2. Try opening EC2 → Access Denied
3. Click **Switch Role**
4. Enter account ID and role name `TemporaryEC2ReadRole`
5. EC2 read-only access is granted temporarily.

---

## ✅ Outcome
- IAM user has no default permissions
- Temporary access is granted using IAM role
- Access is time-bound and automatically expires

