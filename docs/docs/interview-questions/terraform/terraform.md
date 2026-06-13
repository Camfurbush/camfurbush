# Terraform Interview Questions

## What is Infrastructure as Code (IaC)?

- IaC is the practice of defining infrastructure in declarative configuration files and managing it through version control.

## First command for Terraform projects

- `terraform init`: initializes a working directory, downloads providers, and configures the backend.

## Useful Terraform commands

- `terraform init` - initialize directory
- `terraform plan` - show proposed changes
- `terraform apply` - apply changes
- `terraform destroy` - tear down resources
- `terraform output` - read outputs

## What is the Terraform state file?

- Terraform stores information about managed infrastructure in the state file (`terraform.tfstate`). It maps resources in configuration to real-world objects and is necessary for planning and diffs.

## Where to store Terraform state?

- Use remote backends for collaboration and locking (e.g., S3 with DynamoDB locking, GCS, or Terraform Cloud).

## What is state locking?

- State locking prevents concurrent operations from corrupting the state. Many backends (S3+DynamoDB, GCS) support locking.
- Each Terraform configuration can specify a backend, which defines two main things:
  - Where operations are performed (terraform cloud/enterprise)
  - Where the state is stored
- Preferred backends are Terraform Cloud/Enterprise or Amazon S3 and DynamoDB

## What is State File Locking?

- State file locking is Terraform mechanism in which operations on a specific state file are blocked to avoid conflicts between multiple users performing the same process. When one user releases the lock, then only the other one can operate on that state. This helps in preventing state file corruption. This is a backend operation.
