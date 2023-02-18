# Kubernetes

### What is Kubernetes
Kubernetes is an open-source container management also known as container orchestration tool for automating software deployment, scaling, and management.

### What is Container Orchestration
Orchestration enables developers to easily build containerized applications and services, as well as scale, schedule and monitor those containers.

### Nodes
Nodes are physical or virtual machine in which kubernetes is installed.

### Cluster
Cluster is group of nodes, if one node fails we have our application accessible from other nodes.

## Master
Master is other node in which kubernetes is installed and it manages other nodes

### Components
- API Server
- etcd
- kubelet
- Container Runtime
- Controller
- Scheduler

### Master V/S Worker node
Master has kube-apiserver installed and nodes have kubelet installed (Kubelet is an agent which make sure nodes are healthy) which provides information to master which stores information in etcd (key value storage)

### Minikube
Minikube is a lightweight Kubernetes implementation that creates a VM on your local machine and deploys a simple cluster containing only one node. 
- Download kubectl and minikube to start using minikube

### PODS
A Pod is a group of one or more containers, with shared storage and network resources, and a specification for how to run the containers.

### Replication Controllers
Replication Controller used for high availability, it ensures that a specified number of pod replicas are running at any one time. It also helps load balancing and scaling when demand increases.

###
ReplicaSets replaced replication controllers. A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time.

## Deployments and Updates

### Create Deloyment
```
kubectl create -f deployment.yml
```
### Get Deloyment
```
kubectl get deployments
```
### Update Deloyment
```
kubectl set image deployment/fitness-app mysql=mysql:8.0
```
### Status of Deloyment
```
kubectl rollout status deployment/fitness-app
```
```
kubectl rollout history deployment/fitness-app
```
### Rollback Deloyment
```
kubectl rollout undo deployment/fitness-app
```
### Kubernetes Commands

### kubectl
Kubectl is a Command line tool for communicating with a Kubernetes cluster.

### Kubernetes version running on nodes

```bash
kubectl version
```
### Number of nodes

```bash
kubectl get nodes
```
### Command to create a pod and deploy docker container in PODs

```bash
kubectl run mysql --image mysql
```
### List of PODS in Cluster

```bash
kubectl get pods
```
### Get information about POD

```bash
kubectl describe pod mysql
```
### Additional Information about POD

```bash
kubectl get pods -o wide
```
### Create POD using pod-definition.yml file

```bash
kubectl create -f pod-definition.yml
```
### Delete Pod

```bash
kubectl delete pod pod-name
```
### Edit Pod

```bash
kubectl edit pod pod-name
```

### pod-definition.yml

Kubernetes uses yml file as an input to create pods, replicas, deployments, services and so on,

The yml files contain four top level fields-

- apiVersion:  Depending on what we need to create use apiVersion, for creating pods use version v1
- kind: Type of object we want to create such as Pod
- metadata: Data about the object like name, labels and app.
- spec: Specification 

### Create replica sets

```
kubectl create -f replicaset.yml
```
### Get replica sets

```
kubectl get replicaset
```
### Delete replica sets

```
kubectl delete replicaset replicaset-name
```
### Replace replica sets

```
kubectl replace -f replicaset.yml
```
### Scale replica sets

```
kubectl scale -replicas=6 -f replicaset.yml
```
