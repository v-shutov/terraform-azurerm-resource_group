# Azure Resource Group Module

This Terraform module creates an Azure Resource Group and outputs the resource group ID.

## Usage

To use this module, add the following to your Terraform configuration:

```hcl
module "resource_group" {
  source              = "github.com/v-shutov/terraform-azure-resource-group"
  resource_group_name = "my-resource-group"
  location            = "East US"
}
```

### Inputs

| Name                | Description                          | Type   | Default | Required |
|---------------------|--------------------------------------|--------|---------|----------|
| `resource_group_name` | The name of the resource group         | `string` | n/a     | Yes      |
| `location`            | The location for all resources        | `string` | n/a     | Yes      |

### Outputs

| Name               | Description                           |
|--------------------|---------------------------------------|
| `resource_group_id` | The ID of the created resource group  |

### Example

```hcl
module "resource_group" {
  source              = "github.com/your-repo/terraform-azure-resource-group"
  resource_group_name = "my-rg"
  location            = "West Europe"
}
```

### Requirements

- Terraform `>= 0.12`
- Azure Provider `>= 3.0`

### Provider Configuration
You need to configure the Azure Provider before using this module:
```hcl
provider "azurerm" {
  features {}
  subscription_id = "your-subscription-id"
  tenant_id       = "your-tenant-id"
}
```

### License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
