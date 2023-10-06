`kubectl get all`: Get all the resources
`kubectl get nodes`: List all the running nodes
	`kubectl get nodes -o wide`: List all the running nodes with extra details
`kubectl get pods`: Get the list of pods running
	`kubectl get pods -o wide`: List all the running pods with extra details
`kubectl get replicaset`: Get the list of replicasets running
	`kubectl get replicaset -o wide`: List all the running replicaset with extra details
`kubectl get deployment`:
`kubectl run nginx --image nginx`: Create a pod of nginx image and run inside a node
`kubectl describe pods <podname>`: Get detailed information about the pod.
`kubectl apply -f <filepath>`: Create a resource from the file specified
`kubectl create -f <filepath>`: create a resource from the file specified
`kubectl replace -f <filepath>`: Replace the configuration of replicaset
`kubectl delete pods <podname>`: Delete the pod
`kubectl delete replicaset <name>`: Delete the pod
`kubectl edit replicaset <name>`: Edit the currently running replicaset definition file which is stored in kubernetes memory.
`kubectl scale replicaset <name> --replicas=<number>`: Scale up or down the number of pods in replicaset
`kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1`: Update image in a deployment
`kubectl rollout status deployment/myapp-deployment`: Status of rollout
`kubectl rollout history deployment/myapp-deployment`: History of rollout
`kubectl rollout undo deployment/myapp-deployment`: undo of rollout