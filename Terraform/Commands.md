- `terraform init` :
- `terraform plan` :
- `terraform apply` :
- `terraform destroy` :
- `terraform show`: Used to show the current state of the infrastructure.
- `terraform output`: Print all output variables to console.
	`terraform output <variable>`: Used to output a particular output variable.
- `terraform validate`: Validate the configuration of file. In case of error the line causing the error will be shown with hints to fix it.
- `terraform fmt`: Used to format the configuration files to make it more readable.
- `terraform providers`: To list all the providers currently used in current directory.
	`terraform providers mirror <path>`: Used to mirror the providers needed to another directory.
- `terraform refresh`: used to sync terraform with real world infrastructure. This will be update the state file and not the infrastructure resources. Changes will be applied on next apply.
- `terraform graph`: Used to generate visual dependencies of infrastructure in the configuration files. This command can be run even before `terraform init`. The output can be passed to a graph visualizer tool like graphviz.
- `terraform state`: [[State|State commands]]
- `terraform taint`: Used to mark a resource as tainted. Tainted resources are recreated when `terraform apply` is executed.
- `terraform untaint`: To mark a tainted resource as untainted we can use this command.
- `terraform console`: Connects to the interactive terraform console.
- 
