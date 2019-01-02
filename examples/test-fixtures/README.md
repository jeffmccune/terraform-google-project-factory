# Test Fixtures

This is example illustrates how to set up project fixtures sufficient to run the
[integration tests][integration-tests].  Note the VPC itself is created by the
[test suite][vpc].  A host project is required as input so the test suite knows where
to create the VPC host.

It will do the following:
- Create a folder on an organization named for the developer.
- Create a Shared VPC host project in the folder.

Note: this example requires the service account used by terraform to have the
role resourcemanager.folderCreator . You can grant this role with the command
"gcloud organizations add-iam-policy-binding" as in the example below

```sh
gcloud organizations add-iam-policy-binding 1092662220185 \
  --member="serviceAccount:project-factory-12782@terraform-213322.iam.gserviceaccount.com" \
  --role="roles/resourcemanager.folderCreator"
```

[^]: (autogen_docs_start)


## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| admin_email | Admin user email on Gsuite | string | - | yes |
| billing_account | The ID of the billing account to associate this project with | string | - | yes |
| credentials_path | Path to a Service Account credentials file with permissions documented in the readme | string | - | yes |
| organization_id | The organization id for the associated services | string | - | yes |
| username | The username of the developer.  A folder matching the username is created to contain the VPC host project. (e.g. "jmccune") | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| domain | The organization's domain |
| folder_id | The ID of the folder created for the developer.  Pass this value into the corresponding test suite input variable |
| vpc_host_project_id | The ID of the created VPC host project |

[^]: (autogen_docs_end)

[integration-tests]: https://github.com/terraform-google-modules/terraform-google-project-factory#integration-testingS
[vpc]: https://github.com/terraform-google-modules/terraform-google-project-factory/blob/fef6884/test/fixtures/full/main.tf#L34
