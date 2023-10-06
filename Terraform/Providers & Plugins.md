![[Pasted image 20230826151603.png]]

**Official Providers:** These are developed and maintained by Hashicorp. Examples include key cloud providers, local etc.
**Partner Providers:** These are developed by third party organizations who are authorized hashicorp partners.
**Community Providers:** These are individual contributors.

`terraform init` command shows the version of plugins getting installed. By default the latest version of the plugin is installed.

The format for defining/locating the plugin is as below:
`registry.terraform.io/hashicorp/local` 

- The first part `registry.terraform.io` is the hostname. This value is default value
- The second part `hashicorp` is the organizational namespace. 
- The third part `local` is the name of the plugin.

The versioning can be done using [[Plugin Versioning]].




