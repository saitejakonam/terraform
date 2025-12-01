# 🌐 Terraform Azure Storage Account

This project uses **Terraform** to deploy an **Azure Resource Group** and an **Azure Storage Account** (free-tier friendly).  
It follows best practices, includes clean structure, and is fully GitHub-ready.

---

## 📑 Table of Contents
- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Setup Instructions](#-setup-instructions)
- [Usage](#-usage)
- [Outputs](#-outputs)
- [Cleanup](#-cleanup)
- [Security Notes](#-security-notes)
- [References](#-references)
- [License](#-license)

---

## 📘 Overview

This Terraform configuration automates the deployment of:

- An **Azure Resource Group**
- A **Standard LRS Storage Account** (free-tier safe)
- Optional outputs like Blob endpoint

It is perfect for beginners learning Terraform on Azure or for simple automation workflows.

---

## ✨ Features

- Infrastructure as Code (IaC) using Terraform  
- Modular, clean Terraform structure  
- Free-tier compatible Azure resources  
- Separation of variables and sensitive values  
- GitHub-safe (`terraform.tfvars` is ignored)

---

## 📁 Project Structure

```plaintext
terraform-azure-storage/
├── main.tf               # Terraform resources
├── variables.tf          # Input variables
├── outputs.tf            # Output values
├── terraform.tfvars      # Sensitive values (ignored by Git)
└── .gitignore            # Protects state files & tfvars

## 🛠️ Prerequisites

Ensure the following are installed and configured:

- Terraform  
  ```bash
  terraform -version
  ```

- Azure CLI  
  ```bash
  az --version
  ```

- Login to Azure  
  ```bash
  az login
  ```

- Confirm active subscription  
  ```bash
  az account list --output table
  ```

## ⚙️ Setup Instructions

1. Clone the repository
   ```bash
   git clone https://github.com/saitejakonam/terraform.git
   cd terraform-azure-storage
   ```

2. Create terraform.tfvars (kept local and ignored by Git)
   ```hcl
   subscription_id = "your-subscription-id"
   tenant_id       = "your-tenant-id"
   ```

## 🚀 Usage

- Initialize Terraform
  ```bash
  terraform init
  ```

- Preview changes
  ```bash
  terraform plan
  ```

- Apply configuration
  ```bash
  terraform apply -auto-approve
  ```

This will deploy:
- Resource Group
- Storage Account

## 📤 Outputs

After deployment, Terraform will display:
```
primary_blob_endpoint = https://<account>.blob.core.windows.net/
```

## 🗑️ Cleanup

To remove all deployed resources:
```bash
terraform destroy -auto-approve
```

## 🔒 Security Notes

- Never commit terraform.tfvars or Azure credentials.  
- Ensure .gitignore includes:
  - terraform.tfstate
  - backup state files
  - terraform.tfvars

For production, use Azure Storage as a remote backend for Terraform.