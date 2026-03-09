# EC2 Project 1 — Secure EC2 Deployment with Custom Security Group

## Project Summary
This project demonstrates how to deploy a secure Amazon EC2 instance by applying basic cloud security best practices. Instead of allowing open access, SSH connectivity is restricted to a single trusted IP address using a custom Security Group.

The purpose of this project is to understand how EC2 instances are launched and how Security Groups act as virtual firewalls to control incoming and outgoing traffic.

By implementing this setup, the EC2 server remains protected from unauthorized access while still allowing secure administrative access from the developer's system.

---

## What This Project Demonstrates
- Launching an EC2 instance using Amazon Linux
- Creating and attaching a custom Security Group
- Restricting SSH access to a specific IP address
- Connecting to the instance securely using SSH
- Understanding how Security Groups protect cloud infrastructure

---

## Implementation Steps

1. **Launch an EC2 Instance**
   - Open AWS Management Console
   - Navigate to EC2 → Launch Instance
   - Choose Amazon Linux AMI
   - Select instance type (t2.micro)

2. **Create a Key Pair**
   - Generate a key pair during instance creation
   - Download the `.pem` file securely
   - Use this key for SSH authentication

3. **Configure Security Group**
   - Create a custom Security Group
   - Allow SSH (Port 22) access only from your IP address
   - Block all other inbound traffic
   - Keep outbound traffic allowed (default)

4. **Launch the Instance**
   - Review configuration
   - Launch the EC2 instance
   - Wait until the instance state becomes **Running**

5. **Connect to the Instance**
   - Open terminal or command prompt
   - Use SSH with the downloaded key pair
   - Verify secure access to the server

---

## Outcome
- Successfully deployed a secure EC2 instance
- SSH access restricted to a trusted IP address
- No unnecessary ports exposed to the internet
- Demonstrated understanding of basic EC2 security practices
