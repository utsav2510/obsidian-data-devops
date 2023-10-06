![[Pasted image 20230914153752.png]]
### Docker
a very popular developer tool for creating, working with, and managing containers. In other words, it’s a container _engine_, a system that allows code developed in one computing environment to work in another computing environment. In this way, Docker is really a facilitator and enabler of application development. It’s a software platform that simplifies the process of building, running, managing, and distributing applications, and it achieves this by virtualizing the operating system of the computer on which it’s installed and running.

### ContainerD
containerd is a Docker-developed container runtime that manages the life cycle of a container on a physical or virtual machine (i.e., a host). It creates, starts, stops, and destroys containers. It can also pull container images from container registries, mount storage, and enable networking for a container.

### Docker and ContainerD in Kubernetes
Think of the Docker as a big car with all of its parts: the engine, the steering wheel, the pedals, and so on. And if we need the engine, we can easily extract it and move it into another system.

This is exactly what happened when Kubernetes needed such an engine. They basically said, "Hey, we don't need the entire car that is Docker; let's just pull out its container runtime/engine, Containerd, and install that into Kubernetes."

Read more about why Kubernetes did this in this blog post: [Kubernetes Removed Docker. What Happens Now](https://kodekloud.com/blog/kubernetes-removed-docker-what-happens-now/)"