# Terraform

`1. What is Terraform?`

Terraform is an open-source Infrastructure as Code (IaC) tool that allows you to define, manage, and provision infrastructure resources using declarative code.

`2. How does Terraform work with AWS?`

Terraform interacts with the AWS API to create and manage resources based on the configurations defined in Terraform files.

`3. What is an AWS provider in Terraform?`

An AWS provider in Terraform is a plugin that allows Terraform to interact with AWS services by making API calls.

`4. How do you define resources in Terraform?`

Resources are defined in Terraform using HashiCorp Configuration Language (HCL) syntax in .tf files. Each resource type corresponds to an AWS service.

`5. What is a Terraform state file?`

The Terraform state file maintains the state of the resources managed by Terraform. It's used to track the actual state of the infrastructure.

`6. How can you initialize a Terraform project?`

You can initialize a Terraform project using the terraform init command. It downloads required provider plugins and initializes the backend.

`7. How do you plan infrastructure changes in Terraform?`

You can use the terraform plan command to see the changes that Terraform will apply to your infrastructure before actually applying them.

`8. What is the terraform apply command used for?`

The terraform apply command applies the changes defined in your Terraform configuration to your infrastructure. It creates, updates, or deletes resources as needed.

`9. What is the purpose of Terraform variables?`

Terraform variables allow you to parameterize your configurations, making them more flexible and reusable across different environments.

`10. How do you manage secrets and sensitive information in Terraform?`

Sensitive information should be stored in environment variables or external systems like AWS Secrets Manager. You can use variables to reference these values in Terraform.

`11. What is remote state in Terraform?`

Remote state in Terraform refers to storing the state file on a remote backend, such as Amazon S3, instead of locally. This facilitates collaboration and enables locking.

`12. How can you manage multiple environments (dev, prod) with Terraform?`

You can use Terraform workspaces or create separate directories for each environment, each with its own state file and variables.

`13. How do you handle dependencies between resources in Terraform?`

Terraform automatically handles dependencies based on the resource definitions in your configuration. It will create resources in the correct order.

`14. What is Terraform's "apply" process?`

The "apply" process in Terraform involves comparing the desired state from your configuration to the current state, generating an execution plan, and then applying the changes.

`15. How can you manage versioning of Terraform configurations?`

You can use version control systems like Git to track changes to your Terraform configurations. Additionally, Terraform Cloud and Enterprise offer versioning features.

`16. What is the difference between Terraform and CloudFormation?`

Terraform is a multi-cloud IaC tool that supports various cloud providers, including AWS. CloudFormation is AWS-specific and focuses on AWS resource provisioning.

`17. What is a Terraform module?`

A Terraform module is a reusable set of configurations that can be used to create multiple resources with a consistent configuration.

`18. How can you destroy infrastructure created by Terraform?`

You can use the terraform destroy command to remove all resources defined in your Terraform configuration.

`19. How does Terraform manage updates to existing resources?`

Terraform applies updates by modifying existing resources rather than recreating them. This helps preserve data and configurations.

`20. Can Terraform be used for managing third-party resources?`

Yes, Terraform has the capability to manage resources beyond AWS. It supports multiple providers, making it versatile for managing various cloud and on-premises resources.

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

`8. You have 20 servers created through Terraform but you want to delete one of them. Is it possible to destroy a single resource out of multiple resources using Terraform?`

Yes, it is possible. We can use the terraform destroy -target command followed by the resource type and name to destroy a specific resource.

Here's an example:

```bash
terraform destroy -target=aws_instance.my_instance
```

In this example, only the AWS instance named **`my_instance`** would be destroyed, leaving other resources managed by Terraform intact.

`9. Your infrastructure contains database passwords and other sensitive information. How can you manage secrets and sensitive data in Terraform?`

Managing secrets and sensitive data in Terraform require careful consideration to ensure security. Best practices include:

- Never Hardcode secrets in your Terraform code
- Storing secrets outside of version-controlled files, using tools like HashiCorp Vault or cloud-specific secret management services.
- Utilizing Terraform input variables or environment variables to pass sensitive values securely during runtime.

By following these practices, you can protect sensitive information and minimize the risk of exposing secrets unintentionally.

`10. If Your company is looking ways to enable HA. How can you perform blue-green deployments using Terraform?`

- **Blue-Green Deployments in Terraform:**
    - **Concept:** Involves creating two identical environments: blue and green.
    - **Implementation:** Terraform facilitates this by defining two sets of infrastructure resources with slight variations.
    - **Example:** Different AWS Auto Scaling Groups or Azure Virtual Machine Scale Sets for blue and green environments.
    - **Deployment Process:**
        1. **Provisioning:** Create the new environment (green) alongside the existing one (blue).
        2. **Testing:** Validate the green environment to ensure it functions correctly.
        3. **Traffic Switching:** Update the load balancer or DNS records to route traffic from blue to green.
           
<img src="https://github.com/user-attachments/assets/9c1b88d3-fc9e-4693-8e8e-a55ecc2890d5" width="600" height="350">

Reference: https://developer.hashicorp.com/terraform/tutorials/aws/blue-green-canary-tests-deployments
