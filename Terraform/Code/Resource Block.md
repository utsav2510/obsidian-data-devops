
It is used to define a resource. The syntax is as shown below. ![[Pasted image 20230826141626.png]]

### Linking Resource Attributes
We can use the attributes returned by 1 resource block into another resource block. The terraform documentation for the resource blocks lists the attributes returned after running terraform apply.
![[Pasted image 20230828170533.png]]

We can use the following for string interpolation of returned values.
`${<resource_type>.<resource_name>.<attribute_name>}`

### Resource Dependency

Resource dependency are defined so that when the resources are created the dependent resources are created after the main resource. Similarly when the resources are destroyed/deleted the dependent resources are deleted first.
#### Implicit Dependency
As shown in above image implicit dependency is created when the output of one resource is used in another resource.

#### Explicit Dependency
To define explicit dependency of one resource to another we can use the `depends_on` tag.
![[Pasted image 20230828173244.png]]

#### Lifecycle Rules
lifecycle block can be added inside the resource block. To create the resource before destroying the older one use following inside resource block:
```hcl
lifecycle {
	create_before_destroy = true
}
```

To prevent destroying use below in resource block:
```hcl
lifecycle {
	prevent_destroy = true
}
```

Terraform will prevent any changes happening which needs a resource to be destroyed. 

We can also pass a list of attributes inside ignore_changes in the lifecycle block to ignore the changes of a particular attribute in that resource.

```hcl
reource "aws_instance" "webserver" {
	ami = "somaevalue"
	instance_type = "somevalue"
	tags = {
		Name = "ProjectA-Webserver"
	}
	lifecycle {
		ignore_changes = [tags]
	}
}
```

Now if any changes are made to tags attribute, terraform will ignore those changes.
![[Pasted image 20230831160308.png]]

### Meta Arguments
#### Count Function
We can specify count attribute in resource block to specify the number of instances of the resources to be created.

```hcl
variable "filename" {
	default = [
		"/root/cat.txt",
		"/root/dog.txt"
	]
}

resource "local_file" "pet" {
	filename = var.filename[count.index]
	count = length(var.filename)
}
```

This will create files with names defined in variable *filename*. However, changing the name of 1 file in the variable or adding/deleting values in variables will delete and recreate all the files. All resources can be accessed using zero indexed `pet[i]

#### For Each 
when the infrastructure is created using count the resources are created as list. When we update the list all the items are recreated. To overcome this, we can use **for_each** function.
This creates the resources as a map and not a list.

```hcl
variable "filename" {
	default = [
		"/root/cats.txt",
		"/root/dogs.txt"
	]
}

resource "local_file" "pets" {
	filename = each.value
	for_each = toset(var.filename)
}
```

![[Pasted image 20230901122841.png]]

