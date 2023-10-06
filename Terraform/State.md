*terraform.tfstate* file is a `JSON` format file which acts as a single source of truth for all the resources created. It contains the complete details about the resources created.
It is automatically created when the `terraform apply` command is executed for the first time.
It is refreshed every time the configuration file is changed. This file helps terraform to create execution plan.
State file also keeps the metadata of resources. This also tracks dependency i.e. if the dependent resource is changed the main resource will also be updated.

It contains sensitive information in plain text without encryption.

### Commands
- `terraform state show <provider_name>.<resource_name>`: List the properties of the resource as stored in tfstate file.
- `terraform state list`: List the name of resources managed in the state file.
	- `terraform state list <resource name>`: Used to validate and list name of matching resource.
- `terraform state mv <SOURCE> <DESTINATION>`: Used to move a resource from 1 state file to another or to rename a resource.
- `terraform state pull`: Pulls the remote state file and displays it in console. The output can be passed to JSON query tools to further filter the data.
- `terraform state rm <provider_name>.<resource_name>`: This will remove the resource from state file and the resource will no longer be managed by terraform. However, this will not delete the resource.
- 