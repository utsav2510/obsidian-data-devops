By default Terraform downloads the latest available provider plugin. If needed we can specify the specific version. To see the available versions for a particular provider we can visit the terraform documentation and select the particular version of the provider.
Eg: To select google version 4.79.0 instead of latest we can use:
```hcl
terraform {
  required_providers {
    google = {
      source = "hashicorp/google"
      version = "4.79.0"
    }
  }
}
```

We can also specify versioning like below:
`version = "!= 4.79.0"`: Not equal to 4.79.0
`version = "< 4.79.0"`: Less than
`version = "> 4.79.0"`: Greater than
`version = > 1.2.0, < 2.0.0, != 1.4.0`: combination of 3 conditions
`version = "~> 1.2.0"` : This will download either 1.2.0 or any version up to 1.2.9
`version = "~> 1.2"` : This will download either 1.2 or any version up to 1.9

