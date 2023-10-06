- `len(<input>)`: Get the length of a list, set etc.
- `file(<filepath>)`: Get the contents of a file.
- `toset(<list>)`: Convert list to set
- `max(<numbers>)`: return the maximum number
- `min(<numbers>)`: return the minimum number
	suppose we have a variable defined as below.
	```hcl
	variable "num" {
	 type = set(number)
	 default = [250,10,25,1998]
	}
	```
	we can then use the function like this - `min(var.num...)`.
- `ceil(<number>)`: Round up
- `floor(<number>)`: Round down
- `split(<separator>,<string>)`: splits the string by the separator and returns a list.
- `lower(<string>)`
- `upper(<string>)`
- title
- substr
- join
- index
- element
- contains
- keys
- values
- lookup
- 