A **Pod** is the smallest object that can be created in Kubernetes.  It can have 1 or more containers inside it. It is hosted inside a [[Node]].
Containers on the same pod share same storage and network space and can connect with each other using localhost.

To scale application we don't add/remove containers from a pod, instead we add/remove pods which hosts containers.

![[Pasted image 20230914160436.png]]
