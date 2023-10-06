We can provisioners block inside resource block. By default provisioners are run after resources are created. For eg: `remote-exec` block can be used to run scripts in AWS EC2 instances.
![[Pasted image 20230913165425.png]]

We can use the `when` block to run provisioner at a specific event.
![[Pasted image 20230913165618.png]]

If the command inside the provisioner fails the `terraform apply` command also fails by default. We can use the `on_faliure`  block inside the provisioner to change this default behavior.
![[Pasted image 20230913165844.png]]
