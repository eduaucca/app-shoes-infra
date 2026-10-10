# App Shoes Infra - Terraform & Azure Platform

Infrastructure as Code (IaC) and platform provisioning repository for the App Shoes ecosystem.

It centralizes network configuration, clusters, container registries, and security policies in Microsoft Azure, ensuring a modular, repeatable deployment aligned with Zero Trust standards.

## Cloud Architecture

- **Cloud Provider:** Microsoft Azure
- **Orchestration:** Terraform (modularized)
- **Kubernetes Cluster:** Azure Kubernetes Service (AKS) with OIDC (OpenID Connect) enabled.
- **Container Registry:** Azure Container Registry (ACR).
- **Storage:** Private storage account with encryption at rest.
- **Identities and Security:** Azure Managed Identities and Federated Identity Credentials to link Kubernetes service accounts with Azure permissions without exposing static secrets.

## Repository Structure

- `terraform/`: HCL source code organized by components to provision the network, resource group, AKS cluster, ACR, and private storage account.

## Infrastructure Deployment

To initialize and apply infrastructure changes in your Azure subscription, run the following commands within the corresponding directory:

```bash
cd terraform

# Log in to Azure CLI
az login

# Initialize providers and Terraform modules
terraform init

# Review the execution plan
terraform plan

# Apply the configuration
terraform apply
