# IAM Project 2 — IAM Role for EC2 (Password-less Secure Access)

## Project Summary
This project demonstrates how an Amazon EC2 instance can securely access Amazon S3 using an IAM Role instead of storing AWS credentials on the server. In traditional setups, developers often configure access keys and secret keys inside servers, which creates a security risk if those credentials are exposed.

AWS provides IAM Roles to solve this problem. By attaching an IAM Role to an EC2 instance, the instance receives temporary credentials automatically from AWS and can access permitted services securely without storing any keys.

This project implements that best practice by allowing an EC2 instance to read data from an S3 bucket using an IAM Role with read-only permissions.

---

## Objective
The objective of this project is to demonstrate secure service-to-service authentication in AWS by using IAM Roles instead of static credentials.

---

## AWS Services Used
- Amazon EC2
- AWS IAM (Identity and Access Management)
- Amazon S3

---

## Architecture Overview
1. An IAM Role is created with permission to read objects from Amazon S3.
2. The role is trusted by the EC2 service.
3. The IAM Role is attached to an EC2 instance.
4. The EC2 instance accesses S3 using temporary credentials automatically provided by AWS.

---

## Implementation Steps

### Step 1: Create an S3 Bucket
1. Go to AWS Console.
2. Open the S3 service.
3. Click **Create bucket**.
4. Provide a unique bucket name.
5. Keep the default settings and create the bucket.

---

### Step 2: Create an IAM Role for EC2
1. Go to **IAM** in the AWS Console.
2. Select **Roles**.
3. Click **Create role**.
4. Choose **AWS service** as the trusted entity.
5. Select **EC2** as the use case.
6. Click **Next**.

---

### Step 3: Attach Permissions
1. Search for the policy **AmazonS3ReadOnlyAccess**.
2. Select the policy.
3. Click **Next**.
4. Provide the role name:

```
EC2_S3_Access_Role
```

5. Click **Create role**.

---

### Step 4: Launch an EC2 Instance with IAM Role
1. Go to **EC2 Dashboard**.
2. Click **Launch Instance**.
3. Select **Amazon Linux** as the AMI.
4. Choose instance type **t2.micro**.
5. In **Advanced details**, locate **IAM instance profile**.
6. Select the role:

```
EC2_S3_Access_Role
```

7. Configure security group to allow SSH access.
8. Launch the instance.

---

### Step 5: Connect to EC2 Instance
1. Select the EC2 instance.
2. Click **Connect**.
3. Use **EC2 Instance Connect** or SSH.
4. Access the terminal of the instance.


---

## Key Learning Outcomes
- Understanding IAM Roles and trust relationships
- Secure authentication between AWS services
- Avoiding the use of static AWS credentials
- Implementing the principle of least privilege

---

## Conclusion
This project demonstrates a secure and recommended AWS practice where EC2 instances access other AWS services using IAM Roles instead of storing credentials. This approach improves security by providing temporary credentials and reducing the risk of credential leakage.
