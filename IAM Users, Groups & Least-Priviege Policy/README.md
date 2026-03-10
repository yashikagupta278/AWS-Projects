# IAM Project 1 – Users, Groups & Least Privilege Policy

## Project Summary
This project demonstrates how to implement access control in AWS using IAM Users, Groups, and Custom Policies while following the **Principle of Least Privilege**.

Instead of giving full access to every user, permissions are carefully designed based on roles. Different users receive only the permissions required to perform their tasks.

This project simulates a real-world scenario where different team members (Developers and Interns) require different levels of access to AWS resources.

---

## Project Scenario

Two types of users are created:

**Developers**
- Can read and write objects in Amazon S3.
- Can view EC2 instances (read-only access).

**Interns**
- Can only read objects from Amazon S3.
- Cannot access EC2 resources.

This setup ensures that sensitive infrastructure cannot be modified by users who do not require such permissions.

---

## AWS Services Used

- AWS IAM
- Amazon S3
- Amazon EC2

---

## What This Project Demonstrates

- Creating custom IAM policies
- Implementing role-based access control
- Managing permissions using IAM groups
- Assigning users to groups
- Testing real access permissions
- Applying the principle of least privilege

---

## Steps Performed in This Project

### Step 1 – Create IAM Policies
Two custom policies are created.

**DeveloperPolicy**
- Allows S3 object read and write access
- Allows read-only access to EC2

**InternPolicy**
- Allows read-only access to S3
- No EC2 permissions

---

### Step 2 – Create IAM Groups
Two IAM groups are created to manage permissions easily.

**Developers Group**
- Attached with DeveloperPolicy

**Interns Group**
- Attached with InternPolicy

Users added to these groups automatically inherit their permissions.

---

### Step 3 – Create IAM Users
Two IAM users are created to simulate real users.

**developer_user**
- Added to Developers group

**intern_user**
- Added to Interns group

Each user receives permissions through their group membership.

---

### Step 4 – Test the Permissions
The IAM sign-in URL is used to log in with each user and verify their permissions.

**developer_user**
- Can upload and delete objects in S3
- Can view EC2 instances

**intern_user**
- Can read S3 objects
- Cannot upload or delete objects
- Cannot access EC2

---

## Key Learning Outcomes

- Understanding IAM architecture
- Designing secure permission models
- Implementing least privilege access
- Managing access using groups instead of individual policies
- Validating permissions using test users

---

## Conclusion

This project demonstrates how IAM can be used to enforce **secure, role-based access control** in AWS environments. By separating permissions between Developers and Interns, we ensure that users only have access to the resources required for their responsibilities.
