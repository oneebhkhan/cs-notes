It is a program that allows you to run [[Kubernetes]] on your machine.

Minikube creates **a single-node Kubernetes cluster on your computer**, for experimentation with Kubernetes and daily development work.

**Load Balancers** are not available in a Minikube env.

### Uses
1. Learn and experiment quickly
2. Examine key Kubernetes functionality
3. Experiment with Kubernetes' extensibility
4. Quickly learn new frameworks/language
5. Use as a proof-of-concept tool

### Commands
`minikube service list [flags]` -> List the URL(s) of the services in a given namespace if used with `-n SERVICE`

`minikube service [flags] SERVICE` -> Returns the Kubernetes URL(s) for service(s) in your local cluster.