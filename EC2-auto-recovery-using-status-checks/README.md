# EC2 Auto-Recovery Using Status Checks

## Project Summary
This project demonstrates how to enable **EC2 Auto-Recovery** in Amazon Web Services (AWS) to create a self-healing infrastructure. Auto-Recovery automatically restores an EC2 instance if the underlying AWS hardware fails. The instance is recovered on new hardware while keeping the **same instance ID, public IP, and attached EBS volumes**, ensuring minimal downtime and no data loss.

The goal of this project is to understand how AWS monitors instance health using **status checks** and how enabling auto-recovery improves system reliability in production environments.

---

## What We Are Doing in This Project
In this project, we configure an EC2 instance and enable **automatic recovery** using AWS status checks. The instance is continuously monitored by AWS, and if a system-level failure occurs, AWS automatically recovers the instance without requiring manual intervention.

This demonstrates how cloud infrastructure can maintain **high availability and reliability** with built-in monitoring and recovery mechanisms.

---

## AWS Services Used
- Amazon EC2
- Amazon EBS (Elastic Block Store)

---

## Steps Performed

1. **Launch an EC2 Instance**
   - Create or use an existing EC2 instance.
   - Ensure the instance is in a running state.

2. **Check Instance Status Monitoring**
   - Open the EC2 console.
   - Navigate to the **Status Checks** tab.
   - Verify both **System Status Check** and **Instance Status Check** are passing.

3. **Enable Auto-Recovery**
   - Select the EC2 instance.
   - Go to **Actions → Instance Settings → Modify Auto Recovery**.
   - Enable the auto-recovery option.

4. **Verify Storage**
   - Open the **Storage tab**.
   - Confirm that the instance has an attached **EBS volume**.

5. **Validation**
   - Confirm that auto-recovery is enabled in instance settings.
   - Verify that status checks are passing.

---

## Expected Result
- EC2 instance is continuously monitored.
- If a system failure occurs, AWS automatically recovers the instance.
- Instance ID and attached EBS storage remain unchanged.
- Downtime is minimized without manual intervention.

---

## Key Learning
- Understanding EC2 status checks.
- Difference between system and instance health monitoring.
- Implementing self-healing infrastructure using AWS Auto-Recovery.
- Ensuring reliability and availability in cloud environments.
