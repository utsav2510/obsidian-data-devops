![[Pasted image 20230831162825.png]]

Syntax for data block is similar to resource block. It is used to fetch details about a resource that is not defined or maintained using current terraform directory.

The attributes passed to this block should be sufficient enough to identify a particular resource. The attributes for each type of resource is mentioned in the documentation. 
Unlike resource block, data block is used only to read the information about the resource and cannot be used to update the same.