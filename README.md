# AWS Infrastructure using Terraform

![image](https://github.com/user-attachments/assets/aeb76b14-88ef-49fd-b522-8102c4f5f8bf)


This repository contains Terraform scripts to set up an AWS infrastructure with a VPC, subnets, security groups, EC2 instances, an Application Load Balancer (ALB), and an S3 bucket.

## Prerequisites

- AWS CLI installed and configured
- Terraform installed
- An AWS account

## Infrastructure Overview

The Terraform configuration sets up the following:

- A **VPC** with CIDR block `10.0.0.0/16`
- Two **public subnets** in different availability zones
- An **Internet Gateway** for public access
- A **Route Table** with a default route to the Internet Gateway
- A **Security Group** allowing HTTP and SSH traffic
- Two **EC2 instances** running Apache web server
- An **Application Load Balancer (ALB)** distributing traffic across EC2 instances
- An **S3 bucket** for storing assets

## File Structure

```
.
├── main.tf            # Terraform configuration for AWS resources
├── variables.tf       # Variables used in Terraform
├── userdata.sh        # User data script for EC2 instance 1
├── userdata1.sh       # User data script for EC2 instance 2
├── outputs.tf         # Output configuration
└── README.md          # Documentation
```

## Setup and Deployment

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/aws-terraform-project.git
cd aws-terraform-project
```

### 2. Initialize Terraform
```bash
terraform init
```

### 3. Plan the Deployment
```bash
terraform plan
```

### 4. Apply the Configuration
```bash
terraform apply -auto-approve
```

### 5. Access the Load Balancer
Once the deployment is complete, you can find the ALB DNS name from the output:
```bash
echo $(terraform output loadbalancerdns)
```
Open the URL in a web browser to see the deployed website.

## Cleanup
To destroy all resources and avoid extra costs:
```bash
terraform destroy -auto-approve
```

## Author
[Your Name]

## License
This project is licensed under the MIT License.


