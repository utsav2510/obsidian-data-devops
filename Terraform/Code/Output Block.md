Used to define output variable that will be shown on screen when running `terraform apply` or `terraform output`.

```hcl
output pet-name {
	value = "Mr. C"
	Description = "Variable to store pet name"
}
```

These variables can be used to pass the values to other scripts such as Ansible playbook or Shell scripts.
