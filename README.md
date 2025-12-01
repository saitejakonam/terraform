# terraform
🌐 Terraform Azure Storage Account

This project uses Terraform to deploy an Azure Resource Group and an Azure Storage Account (free-tier friendly).
It follows best practices, includes clean structure, and is fully GitHub-ready.

📑 Table of Contents

Overview

Features

Project Structure

Prerequisites

Setup Instructions

Usage

Outputs

Cleanup

Security Notes

References

License

📘 Overview

This Terraform configuration automates the deployment of:

An Azure Resource Group

A Standard LRS Storage Account (free-tier safe)

Optional outputs like Blob endpoint

It is perfect for beginners learning Terraform on Azure or for simple automation workflows.

✨ Features

Infrastructure as Code (IaC) using Terraform

Modular, clean Terraform structure

Free-tier compatible Azure resources

Separation of variables and sensitive values

GitHub-safe (terraform.tfvars is ignored)

📁 Project Structure
terraform-azure-storage/
├── main.tf               # Terraform resources
├── variables.tf          # Input variables
├── outputs.tf            # Output values
├── terraform.tfvars      # Sensitive values (ignored by Git)
└── .gitignore            # Protects state files & tfvars

🛠️ Prerequisites

Make sure you have the following installed:

✔ Terraform
terraform -version

✔ Azure CLI
az --version

✔ Login to Azure
az login

✔ Confirm active subscription
az account list --output table

⚙️ Setup Instructions
1️⃣ Clone the repo
git clone https://github.com/saitejakonam/terraform.git
cd terraform-azure-storage

2️⃣ Create terraform.tfvars

Create a file named terraform.tfvars (auto-ignored by .gitignore):

subscription_id = "your-subscription-id"
tenant_id       = "your-tenant-id"


Replace with your actual Azure subscription and tenant values.

🚀 Usage
Initialize Terraform
terraform init

Preview the deployment
terraform plan

Apply the configuration
terraform apply -auto-approve


This will create:

Resource Group

Storage Account

📤 Outputs

After applying, Terraform will display useful outputs such as:

primary_blob_endpoint

Example:

primary_blob_endpoint = https://myterraformstorage.blob.core.windows.net/

🗑️ Cleanup

To remove all deployed resources:

terraform destroy -auto-approve

🔒 Security Notes

Never commit terraform.tfvars or Azure credentials.

Always use .gitignore to protect:

State files

Backup state

Sensitive variable files

Use Azure Storage for remote backend in real projects.