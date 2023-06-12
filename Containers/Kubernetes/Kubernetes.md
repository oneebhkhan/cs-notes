- Kubernetes is **an orchestration solution for [[Containers]]**
- Kubernetes can be considered a (distributed) OS for a distributed container environment - over a cluster of machines. 

## Introduction
1. Traditional Deployment -> Apps on OS on Hardware
	- Deploying apps
	- Scheduling processor for apps
	- OS provides security for apps
2. Virtualized Deployment -> Apps on VM on Hypervisor on OS on Hardware
3.  [[Containers]] Deployment -> Apps in Container on Container Runtime on OS on Hardware
	* can be considered a lightweight virtualized deployment
	- Images are run on Container Runtime (e.g. Docker Images on Docker Runtime)
### **Declarative vs. Imperative Approach of Creating Kubernetes Resources**
Declarative way - creating a yaml file.
Imperative way - via CLI e.g. `kubectl create configmap ...`

## Kubernetes Architecture
- **Control Plane (Master Nodes for Cluster)**
	- Clusters have redundant masters
	- Ctrl Plane has:
		1. Controller Manager
		2. Etcd (?)
		3. Scheduler
		4. Kube Server
			- Kubectl -> CLI 
			- APIs available
	- All cloud providers have their own *flavours* of Kubernetes, e.g. in how they communicate with controller
- **Worker Nodes**
	- Nodes (Cloud Provider dependent, e.g. incase of AWS they are EC2 Nodes)
	- Nodes can be grouped so that they are optimized for their requirements (e.g. compute opitimized, storage optimized, I/O optimized)
	- Nodes comprise of:
		1. Kubelet
			- Communicates with Kube Server
		2. Pods 
			* Each node runs a container runtime (e.g. Docker) inside a **pod**
			* Pod is the smallest unit of work you can deploy on your cluster. Microservice is bundled up into a pod and deployed. Pod is essentially a container. You can also have multiple containers in one pod (e.g. closely related services would be deployed together.)
			* There are multiple types of pods.
				1. ReplicaSet
					* Ensures specified number of pods are running 
				2. Deployment
					* Servers launched as deployment. They are up 24/7
				3. Daemonset
					* Ensures that an instance of pod will run on all nodes e.g. Health Monitoring (APM, Cluster monitoring tools) instead of any one node 
				4. StatefulSet
					* Kubernetes is best for stateless scenarios **(e.g.??)** however there are cases where we need states or persistence **(e.g. Yugabyte)**
				5. Job and CronJob
					* Either invoked on an ad-hoc/one-time basis
					* Or where they are run on a scheduled basis
					* We can decide what to do in case of failure/unsuccessful runs of Jobs
				* CronJobs and Deployments are the most common types of pods
			* Typically we don't deploy just a pod 
* **Load Balancer**
	* ingress into Cluster is done via load balancer which is the only part exposed to the internet
	* Application Load Balancer is programmed to communicate to an **Reverse NGINX proxy (?)**

## Kubernetes Features
* **Autoscaling**
	* Ability to tie pod creation with metrics via autoscaling.
	1. Horizontal pod autoscaling
		* Metric can be internal to cluster or external in which case you can specify a range of pods min to max 
			* Internal Example: CPU utilization 
			* External Example: SQS queue depth
	2. Vertical pod autoscaling
		* Increase internal resources allocated to pod, e.g. increase memory allocated to the pod
	3. Cluster autoscaling
		* You have to configure min and max number of nodes per cluster. 
* **Services**
	* How do you address an API deployed on a pod which might change from node to node, or cluster to cluster.
		* Ability to address pods is through **Services**
	* Once a pod is deployed its tied to a service
	* Services are the addressable component
	1. Load Balancer Service:
		- Connects with cloud load balancer. 
		- Drawback - service is connected to internet
		- Drawback - if you create load balancer service for all the microservices then there is a cost incurred.
		- 
- **Namespace**
	- Logical cluster within the larger Kubernetes Cluster

Collection of pods is called a deployment. 
How you address this collection is called a service.

## Configuration
* Configuration is done in YAML file. 
* We only need to write configurations that we want to overwrite, everything else will be handled.
* **replicas:** number of replicas running (? TBC)
* **image:** container image path
* **resources:**  specify requested and limit of cpu and memory, based on this kubernetes will decide which node to use
* **restart policy:** what to do in case of crash
* **strategy:**   
* **config maps:** configuration items available to pods when they start
	real time changes can be done to configs 

## K8s Concepts
1. [[Kind]]
2. [[Custom Resource Definition |CRD]]
3. 

## Kubernetes Networking
* Addressing a service can be done as: `sevice.namespace.svc.cluster.local`


## Kubernetes Tools
1. [[Lens]] 
2. [[Minikube]] is a CLI tool for Kubernetes
3. [[kubectl]]
4. [[Helm]] is a package manager 

## Storage
1. *[[Storage#Persistent Volume |Persistent Volume]]*
2. *[[Storage#Persistent Volume Claim |Persistent Volume Claim]]*
3. *[[Storage#Storage Classes |Storage Classes]]*

Pass data file as config map
* File needs to be in the Helm chart repo?
Mount config as volume to a given path