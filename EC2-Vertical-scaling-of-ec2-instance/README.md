# EC2 Project 3 – Vertical Scaling of EC2 Instance

## Project Summary
This project demonstrates **Vertical Scaling in Amazon EC2** by upgrading the instance type to increase system resources such as CPU and RAM.

Vertical scaling means improving the performance of an existing server by changing it to a more powerful instance type. In this project, an EC2 instance is resized from **t2.micro** to **t2.small** to handle higher workloads.

---

## What We Are Doing in This Project
- Launch or use an existing **EC2 instance**
- Stop the instance to modify hardware configuration
- Change the **instance type (t2.micro → t2.small)**
- Restart the instance
- Verify the upgraded resources using Linux commands

---

## AWS Services Used
- Amazon EC2
- Amazon Linux
- SSH

---

## Steps Performed

1. Launch an EC2 instance with instance type **t2.micro**
2. Stop the EC2 instance from the AWS console
3. Change the instance type to **t2.small**
4. Start the instance again
5. Connect to the instance using SSH
6. Verify the increased memory using the command:


---

## Result
The EC2 instance was successfully resized from **t2.micro to t2.small**, increasing available memory and CPU resources while keeping the same instance and storage.

---

## Key Learning
- EC2 instances can be vertically scaled by modifying their instance type.
- Instance must be **stopped before resizing**.
- **EBS storage and data remain unchanged** during scaling.
- Vertical scaling is useful for improving performance for predictable workloads.
