# Stage 5 — Infrastructure as Code (Terraform & Cloud)

Overview:
- Declarative infra, reproducibility, and state management.
- Use providers to manage cloud resources (AWS, Azure, GCP).

Install:
- Terraform: https://developer.hashicorp.com/terraform/downloads
- Configure provider credentials for chosen cloud (AWS CLI, gcloud, az)

Core commands:
- `terraform init`
- `terraform plan`
- `terraform apply`
- `terraform destroy`

Cloud providers & patterns:
- AWS: S3, EC2, VPC, RDS
- GCP: Compute Engine, Cloud Storage, VPC
- Azure: Resource Groups, VMs, Storage Accounts
- Remote state backends: Terraform Cloud, S3 + DynamoDB lock, GCS, Azure Blob

Tasks:
- Write a Terraform module that provisions a simple cloud resource (e.g., S3 bucket or Storage Account).
- Create a separate network (VPC / VNet) and a small VM or managed instance.
- Configure remote state (S3/GCS/Blob) with locking.
- Use variables and outputs; create a reusable module.
- Add a CI job that runs `terraform fmt`, `terraform validate`, and `terraform plan` on PRs.

Exercises:
- Build a Terraform config that sets up a public storage bucket and a tagged VM.
- Modularize the config and test applying in a disposable environment.
- Integrate Terraform plan into GitHub Actions and store plan artifact.

Outcome:
- Provision cloud resources reproducibly, manage state, and automate IaC checks.

References:
- Terraform docs: https://developer.hashicorp.com/terraform
- Provider docs: AWS / Azure / GCP
- Terraform best practices: modules, remote state, workspaces