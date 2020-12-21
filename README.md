# microservices-demo

Install Minikube
______________________
https://minikube.sigs.k8s.io/docs/start/

Install docker

Launch minikube

Build and push docker file.
e.g.
docker build -f src/main/docker/Dockerfile.jvm -t usopan/microservices-demo .

docker push usopan/microservices-demo
# create deployment
kubectl create -f deployment.yaml
# create networking/service
kubectl create -f service.yaml
# create a virtual service
kubectl create -f virtual-service.yaml
# create canary release for your service
kubectl create -f canary.yaml
# create horizontal pod autoscaler
kubectl create -f hpa.yaml



