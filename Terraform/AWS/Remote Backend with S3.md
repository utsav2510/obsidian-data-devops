To implement remote backend with S3 we need the following:
1. An Amazon S3 bucket to store tfstate file.
2. A DynamoDB in AWS to implement state locking.

We need to use below code to implement:
```hcl
terraform {
	backend "s3" {
		bucket = "bucket-name"
		key = "finance/terraform.tfstate"
		region = "us-west-1"
		dynamodb_table = "state-locking"
	}
}
```

