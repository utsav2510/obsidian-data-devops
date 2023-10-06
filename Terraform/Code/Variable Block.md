Used to define variables. We can create a separate file (eg: variables.tf) to maintain the variables.
Variables then can be used in configuration blocks as shown below.
![[Pasted image 20230826164856.png]]
#### Variable Arguments
Variables have 3 arguments to be defined:
- **Default**: default value of the variable
- **Type**: Type of variable. Can be `string`,`number`,`boolean`,`any` ![[Pasted image 20230826165732.png]]
- **Description**: Description of the variable defined.


![[Pasted image 20230826165648.png]]

#### Passing Values to variable
1. Using the default argument in variable block as shown above
2. Instead of passing default values we can pass variables in command line when using terraform apply command.
![[Pasted image 20230828162013.png]]
3. We can also make use of environment variables and pass the variable values by adding `TF_VAR` before the variable values. ![[Pasted image 20230828162652.png]]
4. We can also make use of terraform **variable definition files**. They should have file names *terraform.tfvars* or *terraform.tfvars.json*. To use file names other than "terraform" like *variable.tfvars* we can pass the variable files as argument. `terraform apply -var-file varialble.tfvars`. ![[Pasted image 20230828162853.png]]
5. Similar to variable definition files we have autoload variable definition files. They can have any name with extension *.auto.tfvars* and *.auto.tfvars.json*. 

#### Variable Definition Precedence
![[Pasted image 20230828164259.png]]

Terraform first loads environment variables, then terraform.tfvars, then auto.tfvars in alphabetical order and then command line flags. Therefore, the command line flags have the highest precedence over other.

#### Length Function
Used to return the count of items in a variable list.

`length(<varname>)`




