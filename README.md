# Terraform Mumbai EC2 + VPC Setup

This project uses **Terraform** to deploy an EC2 instance and supporting infrastructure (VPC, subnet, gateway, route table, security group) in the **Mumbai (ap-south-1)** region.

---

## 🚀 What This Creates

- VPC and Subnet (CIDR configurable)
- Internet Gateway + Route Table
- Security Group (SSH open)
- EC2 Instance (Amazon Linux 2)

---

## 📁 Files

- `main.tf`: Main infrastructure config
- `variables.tf`: Variables used
- `terraform.tfvars`: Values for the variables
- `outputs.tf`: Output public IP after apply

---

## ✅ Prerequisites

- AWS Account & Access Key
- Terraform installed: [Download Terraform](https://developer.hashicorp.com/terraform/downloads)
- AWS key pair in Mumbai (e.g., `mumbai-key`)
- Optional: AWS CLI

---

## 🛠️ How to Use

```bash
# 1. Clone repo
git clone https://github.com/gowtham-i-sidharth/terraform-mumbai-ec2.git
cd terraform-mumbai-ec2

# 2. Initialize Terraform
terraform init

# 3. Check configuration
terraform validate

# 4. Preview
terraform plan

# 5. Apply infrastructure
terraform apply -auto-approve

# 6. Get EC2 Public IP
terraform output instance_public_ip

# 7. SSH (example)
ssh -i "mumbai-key.pem" ec2-user@<public-ip>
