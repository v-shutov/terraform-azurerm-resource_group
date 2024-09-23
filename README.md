# Azure Resource Group and Storage Account Module (Educational Purpose)

This Terraform module is created for **educational purposes**. It demonstrates how to create an Azure Resource Group and an Azure Storage Account within that resource group. The module outputs the resource group ID and the storage account ID.

## Usage

To use this module, add the following to your Terraform configuration:

```hcl
module "azure_resources" {
  source                 = "github.com/v-shutov/terraform-azurerm-resource_group_storage"
  resource_group_name    = "my-resource-group"
  location               = "East US"
  storage_account_name   = "mystorageaccount"
}
```

### Inputs

| Name                   | Description                            | Type   | Default | Required |
|------------------------|----------------------------------------|--------|---------|----------|
| `resource_group_name`   | The name of the resource group         | `string` | n/a   | Yes      |
| `location`              | The location for all resources         | `string` | n/a   | Yes      |
| `storage_account_name`  | The name of the storage account        | `string` | n/a   | Yes      |

### Outputs

| Name                    | Description                            |
|-------------------------|----------------------------------------|
| `resource_group_id`      | The ID of the created resource group   |
| `storage_account_id`     | The ID of the created storage account  |

### Example
```hcl
module "azure_resources" {
  source                 = "github.com/v-shutov/terraform-azurerm-resource_group_storage"
  resource_group_name    = "my-rg"
  location               = "West Europe"
  storage_account_name   = "mystorageacct"
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
This project is created for educational purposes and is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.
