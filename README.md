# MyKubernetesCluster
This repository contains a simple Kubernates cluster that host a simple microservice written in JAVA Spring-Boot.

The aim of the repository is to show the core concepts of Kubernates like Deployment, Service, Ingress...

The application encompasses a MongoDB database and a web service.
In the current file, below, there are some of common comand used to build the cluster.

## K8s tools and util commands
### Tools
1. Kind 
2. kubectl

### Base Commands
1. kind create cluster --name < cluster name > 
2. kubectl get nodes
3. kubectl cluster-info
4. kubectl config get-contexts
5. kubectl config current-context
6. kubectl create deployment nginx --image=nginx
7. kubectl get deployments
8. kubectl get pods
9. kubectl expose deployment nginx --port=80 --type=NodePort
10. kubectl get svc
11. kubectl get deployment nginx -o yaml > deployment.yaml
12. kubectl get service nginx -o yaml > service.yaml
13. kubectl delete deployment nginx
14. kubectl delete service nginx
15. kubectl apply -f k8s/
16. kubectl explain service
17. kubectl explain deployment
18. kubectl get pvc <-- this command finds the volumes

#### Command to build a tunnel connection with my db inside cluster
kubectl port-forward svc/mongodb-service 27017:27017

#### Compass connection
mongodb://admin:mia-password-segreta@localhost:27017


### Next step: Command for build a secret
kubectl create secret generic mongodb-pass --from-literal=mongo-root-password=mia-password-segreta
