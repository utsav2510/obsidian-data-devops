# Introduction

Kubernetes uses YAML files to define pods, services, replica sets and deployments. Following is the basic structure of a YAML file used in Kubernetes.
```yml
apiversion: 
kind: 
metadata:
	
spec:
```

The *apiversion* and *kind* fields can be one of the below values based on the type of resource:
![[Pasted image 20230914170717.png]]

# Pods
The basic definition file for a Pod is as below:

*Pod-Definition.yaml*
```yml
apiVersion: v1
kind: Pod
metadata:
	name: Pod1
	labels:
		somekey: somevalue
		somekey2: somevalue2
spec:
	containers:
		 - name: containername
		   image: image
		 - name: containername2
		   image: image2
```

Run below command to bring up the pod.
`kubectl apply -f Pod-Definition.yaml`


# ReplicaSet
The basic definition file for a replicaset is as below:

*replica-set.yaml*
```yml
apiVersion: apps/v1
kind: ReplciaSet
metadata:
	name: RS1
	labels:
		somekey: somevalue
		somekey2: somevalue2
spec:
	template:
		metadata:
			name: Pod1
			labels:
				somekey: somevalue
				somekey2: somevalue2
		spec:
			containers:
				 - name: containername
				   image: image
				 - name: containername2
				   image: image2
	replicas: 3
	selector:
		matchLabels:
			somekey: somevalue
```

The template tag contains the definition of the POD to be used. This helps replicaset to spin up new POD in case the existing POD fails.

The selector tag is used to select the POD that will be managed by the replicaset. This will also check for existing pods. 

`kubectl create -f replica-set.yaml` will create the replicaset.

We can update the `replicas` tag to some other value and then run following command to update
`kubectl replace -f replica-set.yaml`


# Deployments
The YAML for deployments is very much similar to replicaset and looks like below:

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
	name: Deployment1
	labels:
		somekey: somevalue
		somekey2: somevalue2
spec:
	template:
		metadata:
			name: Pod1
			labels:
				somekey: somevalue
				somekey2: somevalue2
		spec:
			containers:
				 - name: containername
				   image: image
				 - name: containername2
				   image: image2
	replicas: 3
	selector:
		matchLabels:
			somekey: somevalue
```

Note: This will also create a replicaset.

# Service

## NodePort


```yml
apiVersion: v1
kind: Service
metadata:
	name: myapp-service
spec:
	type: NodePort
	ports:
		- port: 80
		  targetPort: 80
		  nodePort: 30004
	selector:
		podlabelkey: podlabelvalue
```

## ClusterIP (Default Service)

```yml
apiVersion: v1
kind: Service
metadata:
	name: myapp-service
spec:
	type: ClusterIP
	ports:
		- port: 80
		  targetPort: 80
	selector:
		podlabelkey: podlabelvalue
```
