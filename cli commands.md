## Important Commands:
- kubectl run redis --image=redis --dry-run=client -o yaml > pod.yaml ( ** To create yaml file automatically)

## install hyperhit and minikube
- brew update
- brew install hyperkit
- brew install minikube
- kubectl
- minikube

## create minikube cluster
- minikube start --vm-driver=hyperkit
- kubectl get nodes
- minikube status
- kubectl version

## delete cluster and restart in debug mode
- minikube delete
- minikube start --vm-driver=hyperkit --v=7 --alsologtostderr
- minikube status

## kubectl commands
- kubectl get nodes
- kubectl get pod
- kubectl get services
- kubectl create deployment nginx-depl --image=nginx
- kubectl get deployment
- kubectl get replicaset
- kubectl edit deployment nginx-depl
## Replication Controller
- kubectl create -f replica.yaml
- kubectl get rc
- kubectl replace -f replicat.yml (** To update the replicaset in future)
- kubectl scale --replica=6 -f replica.yaml
- kubectl delete replicaset replica.yaml
## Deployment
- kubectl get all
## Namespaces
- kubectl create -f namespaces.yml --namespace=dev (** To crete Manually)
- kubectl create namespace dev
- kubectl config set-context $(kubectl config current-context) --namespace=dev
- 

## debugging
- kubectl logs {pod-name}
- kubectl exec -it {pod-name} -- bin/bash

## create mongo deployment
- kubectl create deployment mongo-depl --image=mongo
- kubectl logs mongo-depl-{pod-name}
- kubectl describe pod mongo-depl-{pod-name}

## delete deplyoment
- kubectl delete deployment mongo-depl
- kubectl delete deployment nginx-depl

## create or edit config file
- vim nginx-deployment.yaml
- kubectl apply -f nginx-deployment.yaml
- kubectl get pod
- kubectl get deployment

## delete with config
- kubectl delete -f nginx-deployment.yaml
## Metrics
kubectl top The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.
## Create Name Spaces
- kubectl get namespaces
- kubectl create namespace namespace-name
## What are the different commands available by default with kubectl?
 - kubectl --help | less

## How to get more information about Kubernetes objects?
- kubectl explain pods.spec.containers.image | less

## Can we assign serviceaccount to pod when creating the pod declaratively?
- kubectl run --help | grep serviceaccount

## Generate yaml using kubectl run command
- kubectl run nginx --image=nginx --dry-run=client -o yaml &gt; nginx.yaml

## Can we add command and arguments while creating pod declaratively?
- kubectl run nginx --image=nginx --dry-run=client -o yaml --command -- sleep 1000 &gt; nginx-new.yaml
     kubectl run nginx --image=nginx --dry-run=client -o yaml -- sleep 1000 &gt; nginx-new.yaml
 
## Delete all the pods under current namespace
- kubectl delete pods --all

## Switch namespace permanently
- kubectl config set-context --current --namespace=samir

## Show pod labels
- kubectl get pods --show-labels

## Show IP address of the pods and the nodes the pods are scheduled on
- kubectl get pods -o wide

## Show only secrets that are of type Opaque
- kubectl get secrets --field-selector type=Opaque

## Show all pods that have label app=frontend
- kubectl get pods --selector app=frontend
- kubectl get pods -l app=frontend

## Update a pod that has command “sleep 1200” to “sleep 2000”
- sed -i "s/- \"1200\"/- \"2000\"/g" nginx.yaml

## Create a deployment and set replicas=3 in single command
- kubectl create deployment nginx --image=nginx --dry-run=client -o yaml | sed -e "s/replicas: 1/replicas: 2/g" | kubectl create -f -

## Sort secrets by name and save in a file sorted-secrets.txt
- kubectl get secrets --sort-by=metadata.name
---
## Yaml file option check commands
- kubectl explain pods --recursive |less

