`1. What is Terraform and How it works?`

Terraform is an IaC tool that lets you write code to define and manage your infrastructure.

You describe your desired infrastructure in configuration files, Terraform figures out what needs to be done to achieve that state, and then it makes it happen by interacting with cloud providers or other infrastructure platforms.

<img src="https://github.com/user-attachments/assets/691bbdfa-b6e4-458d-8a05-f11ddd18d73a" width="600" height="450">


`2. A DevOps Engineer manually created infrastructure on AWS, and now there is a requirement to use Terraform to manage it. How would you import these resources in Terraform code?`

To import existing AWS resources into Terraform, you can follow  these steps:

1. Write Terraform configuration for the resources you want to manage.
`main.tf`
```
provider "aws" {
    region = "ap-south-1"
}

import {
  id = "i-04cada09773b9e67a"
  to = aws_instance.example
}
```
2. Run `terraform plan -generate-config-out="generated_bucket.tf"` command, using this terraform code is copied to `generated_resources.tf` file.
3. Then copy the code from generated_resources.tf to main.tf file.
4. Run `terraform import` command for each resource, specifying the resource type and its unique identifier in AWS.

```bash
terraform import aws_instance.example <resources-id>
```

Repeat this process for each resource you want to manage with Terraform.

<img src="https://github.com/user-attachments/assets/58114ea4-cd7d-4a52-9421-ed6d798c2722" width="600" height="250">

`3. You have multiple environments - dev, stage, prod for your application and you want to use the same code for all of these environment. How can you do that?`

1. **Terraform Modules**: Code templates for infrastructure components. You define them once, and then you can use them with different configurations for various environments by passing in different parameters.

<img src="https://github.com/user-attachments/assets/b7b30424-1a84-450c-bcd3-0d94f68a885b" width="600" height="650">

2. **Terraform Workspaces**: Provide a way to manage separate states for the same set of configuration files. Each workspace maintains its own state, allowing you to work on different environments concurrently without interfering with each other.

<img src="https://github.com/user-attachments/assets/9792006e-b4ba-455d-8e18-9b3870e6ddae" width="600" height="300">

`4. What is the Terraform state file, and why is it important?`

The Terraform state file is a JSON or binary file that stores the current state of the managed infrastructure. 

State file is like a blueprint that stores information about the infrastructure you manage. 

It's crucial because it helps Terraform understand what's already set up and what changes need to be made. By comparing the desired setup with the current one in the state file, Terraform can make accurate updates to your infrastructure.

<img src="https://github.com/user-attachments/assets/3228b1b4-0df8-4f72-af4c-69d24f3777e5" width="600" height="300">

`5. If Jr DevOps Engineer accidently deleted the state file, what steps should we take to resolve this?`

If the state file is lost

1. **Recover Backup**: If available, restore the state file from a recent backup.
2. **Recreate State**: If no backup exists, manually reconstruct the state by inspecting existing infrastructure and using `terraform import` for missing resources.
3. **Review and Prevent**: Analyze the incident, implement preventive measures, and educate team members on best practices to avoid similar incidents in the future.

`6. What are some best practices to manage terraform state file?`

1. **Remote Storage**: Store the state file remotely (e.g., AWS S3) for safety, collaboration and version control.
2. **State Locking**: Enable state locking to prevent conflicts in concurrent operations.
3. **Access Controls**: Limit access to the state file to authorized users and services.
4. **Automated Backups**: Set up automated backups to prevent data loss.
5. **Environment Separation**: Maintain separate state files for each environment or utilize Terraform workspaces to manage multiple state files.

`7. Your team is adopting a multicloud strategy and you need to manage resources on both AWS and Azure using terraform so how do you structure your terraform code to handle this?`

**Terraform is cloud agnostic.**

1. Set up provider configurations for both AWS and Azure in separate blocks.

```
provider "aws" {
  region = var.aws_region
}

provider "azurerm" {
  features {}
  subscription_id = var.azure_subscription_id
  client_id       = var.azure_client_id
  client_secret   = var.azure_client_secret
  tenant_id       = var.azure_tenant_id
}
```
2. Create Terraform code with separate modules for AWS and Azure resources.

<img src="https://github.com/user-attachments/assets/6b79603a-294e-4ab9-bebd-92c375d24997" width="500" height="200">
