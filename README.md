# microservices-demo
# Prequisites
## Install Minikube
______________________
https://minikube.sigs.k8s.io/docs/start/

## Install docker

## Launch minikube
minikube start

## install istio on minikube 
Follow steps from here
https://medium.com/faun/istio-step-by-step-part-10-installing-istio-1-4-in-minikube-ebce9a4e99c

# Start Deployment

## Build and push docker file.
e.g.
mvn clean package
docker build -f src/main/docker/Dockerfile.jvm -t usopan/microservices-demo .

docker push usopan/microservices-demo
## create deployment
kubectl create -f deployment.yaml
## create networking/service
kubectl create -f service.yaml
## create a virtual service
kubectl create -f virtual-service.yaml
## create canary release for your service
kubectl create -f canary.yaml
## create horizontal pod autoscaler
kubectl create -f hpa.yaml



