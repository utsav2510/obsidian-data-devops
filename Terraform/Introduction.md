Terraform is an Infrastructure as code (IaC) tool. It uses configuration file written in **Hashicorp Configuration Language** (HCL). HCL is designed to be both human and machine-readable for use in infrastructure automation. Terraform supports all the major cloud providers like AWS, Azure, GCP and can also be used to for On-prem environment.

Terraform files have a .tf extension. All the objects managed by terraform is called a resource. It can be a file, server, storage, database etc.

Terraform follows an immutable infrastructure approach i.e. once the resource is created it will update it by deleting and then recreating the same with updated arguments.

### HCL Syntax
HCL is made up of blocks and parameters. Each block arguments is defined inside a set of curly brackets.
```hcl
<block> <parameters> {
	key1 = value1
	key2 = value2
}
```

![[Pasted image 20230826141626.png]]


