# Terraform Azure Provisioning Virtual Machines
Terraform is an open-source infrastructure as code (IaC) tool that enables you to define and manage cloud infrastructure resources using a declarative configuration language. It supports multiple cloud platforms, including Microsoft Azure.

## How it works on Azure
In summary, using Terraform with Azure can help you automate the deployment and management of your Azure resources, while also providing greater control and reproducibility over your infrastructure.

## What this project will do
In this article, you'll learn how to:

- Create a virtual network
- Create a subnet
- Create a public IP address
- Create a network security group and SSH inbound rule
- Create a virtual network adapter card
- Connect the network security group to the network adapter
- Create a storage account for boot diagnostics
- Create SSH key
- Create a virtual machine
- Use SSH to connect to the virtual machine

## Table of Contents
- [Terraform Azure Provisioning Virtual Machines](#terraform-azure-provisioning-virtual-machines)
  - [How it works on Azure](#how-it-works-on-azure)
  - [What this project will do](#what-this-project-will-do)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [Connect into the Virtual Instances](#connect-into-the-virtual-instances)
  - [Usage](#usage)
  - [Contributing](#contributing)
  - [License](#license)

## Installation
You need to first install Terraform on your local machine or a build server. You can download Terraform from the official website or use a package manager like Homebrew.

## Connect into the Virtual Instances
- First you need to run the `terraform output` command to get the SSH key:

`terraform output -raw tls_private_key > id_rsa`

- Run the terraform command below to check more details:

`terraform output public_ip_address`

- Use the SSH to connect into the instance:

`ssh -i id_rsa azureuser@<public_ip_address>`

## Usage
- Azure Account: You must have an active Microsoft Azure account. If you do not have one already, you can sign up for a free Azure trial account.

- Create an Azure service principal: Terraform requires an Azure service principal to authenticate and access your Azure resources. You can create a service principal using the Azure CLI or the Azure portal.

- Configure Terraform provider: Once you have created an Azure service principal, you need to configure the Azure Terraform provider. The provider is a plugin that enables Terraform to interact with Azure resources. You can configure the provider by specifying the Azure authentication details, like client ID, client secret, tenant ID, and subscription ID, in your Terraform configuration file.

- Write Terraform configuration: After configuring the provider, you can write your Terraform configuration files. The configuration files define the desired state of your infrastructure resources, such as virtual machines, storage accounts, or network interfaces. Terraform uses these files to create or modify the resources in Azure.

- Initialize Terraform: Before you can use Terraform to create or modify Azure resources, you need to initialize Terraform in your project directory. The initialization downloads the required Terraform modules and plugins.

- Run Terraform commands: Once you have initialized Terraform, you can run Terraform commands to create or modify Azure resources. For example, you can use the terraform plan command to preview the changes Terraform will make to your infrastructure, and the terraform apply command to apply those changes.

- Destroy resources: When you no longer need the resources you created with Terraform, you can use the terraform destroy command to remove them. This ensures that you are not billed for resources that are no longer in use.

## Contributing
Guidelines for contributing to your project go here.

## License
GitHub GPL License.



