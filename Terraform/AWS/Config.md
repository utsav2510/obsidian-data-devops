AWS Provider for Terraform: https://registry.terraform.io/providers/hashicorp/aws/latest/docs

We can configure the credentials and configuration for providers using below command:

1. Configuring directly in the configuration file

```hcl
provider "aws" {
	region = "us-west-1" 
	access_key = "SDFSDFDCFSD"
	secret_key = "SDDFKNJFDSLGJKNSF"
}
```

Since we store the configuration files in a version control system it is not advisable/best practice to hard code the credentials in configuration file.

2. We can use environment variables to declare these values:
`AWS_REGION`, `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` are the values we can configure as environment variables.

3. Credentials file
 We can use credentials file to store the credentials.
 Best practice is to store the file in: `<user_home>\.aws\config\credentials`
 Store the credentials as below:
```
[default]
aws_access_key_id = SDSDLFNSDIFNS
aws_secret_access_key = DSIBFSIFDBIDS
```

To specify a different credentials file we can mention below command in configuration file:

```
provider "aws" {
	region = "us-west-1" 
	shared_credentials_file = "/path/to/aws_credentials"
}
```
