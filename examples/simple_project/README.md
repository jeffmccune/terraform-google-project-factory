# Simple Project

This example illustrates how to create a simple project.

Expected variables:
- `admin_email`
- `organization_id`
- `billing_account`
- `credentials_path`

[^]: (autogen_docs_start)


## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| admin_email | Admin user email on Gsuite | string | - | yes |
| billing_account |  | string | - | yes |
| credentials_path | Path to a Service Account credentials file with permissions documented in the readme | string | - | yes |
| organization_id |  | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| domain_example | The organization's domain |
| project_info_example | The ID of the created project |

[^]: (autogen_docs_end)
