### IAM User
[[https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_user|IAM User Documentation]]

```hcl
resource "aws_iam_user" "admin_user" {
	name = "John"
	tags = {
		Description = "Technical Team Leader"
	}
}
```

### IAM Policies
![[Pasted image 20230911145649.png]]
We can also define the policy in a separate file within the same directory as configuration file and use it as below:
![[Pasted image 20230911150054.png]]
