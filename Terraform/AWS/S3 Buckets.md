S3 buckets can be created and managed using terraform. 
[[https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket|s3 with terraform]]

```hcl
resource "aws_s3_bucket" "example" {
  bucket = "my-tf-test-bucket"

  tags = {
    Name        = "My bucket"
    Environment = "Dev"
  }
}
```

We can add objects to the buckets using the following command:
```hcl
resource "aws_s3_bucket_object" "object" {
  bucket = "your_bucket_name" # aws_s3_bucket.bucknetname.id
  key    = "new_object_key"
  source = "path/to/file"
}
```


