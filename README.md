<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c9534e8e-af93-42b6-b70f-b58eb44439dd" />
# 🚀 3-Tier Architecture on AWS using Terraform

This project provisions a production-ready 3-tier architecture on AWS using modular Terraform design.

The infrastructure follows best practices for scalability, high availability, and security.


## 🏗 Architecture Overview

This 3-Tier Architecture includes:

### 🌐 1️⃣ Networking Layer (modules/networking)

• Custom VPC
• Public Subnets across multiple AZs
• Private Subnets across multiple AZs
• Internet Gateway
• NAT Gateway
• Route Tables
• Security Groups

### 🖥 2️⃣ Application Layer (modules/autoscaling)

• Application Load Balancer (ALB)
• Target Group
• Launch Template
• Auto Scaling Group
• EC2 Instances in Private Subnets
• IAM Roles and Instance Profile

### 🗄 3️⃣ Database Layer (modules/database)

• Amazon RDS MySQL
• DB Subnet Group
• Private Subnet Deployment
• Dedicated Security Group


## 📂 Project Structure

3-tier-architecture/

├── modules/
│   ├── networking/
│   ├── autoscaling/
│   └── database/
│
├── main.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
├── providers.tf
├── versions.tf
├── .terraform.lock.hcl
├── .gitignore
├── LICENSE
└── README.md

## ⚙ Tools & Technologies Used

• Terraform
• AWS
• EC2
• Auto Scaling
• RDS
• Application Load Balancer
• IAM
• CloudWatch

## ⚙ Prerequisites

Make sure you have:

• AWS Account
• AWS CLI configured
• Terraform >= 1.x
• IAM permissions to create AWS resources

## 🚀 Deployment Steps

terraform init
terraform validate
terraform plan
terraform apply

To destroy infrastructure and avoid charges:

terraform destroy

## 🔐 Security Best Practices Implemented

• RDS deployed in private subnets
• EC2 instances deployed in private subnets
• ALB deployed in public subnets
• Security group-based access control
• IAM roles instead of hardcoded credentials
• Sensitive values not committed to Git


## 📈 High Availability & Scalability

• Multi-AZ deployment
• Auto Scaling Group for web tier
• Load balancing across EC2 instances
• NAT Gateway for secure outbound access
• Modular design for production-ready workloads


## 🌟 Why Modular Terraform?

Using modules provides:

• Reusability
• Clean project structure
• Easier maintenance
• Clear separation of concerns
• Scalable infrastructure design


