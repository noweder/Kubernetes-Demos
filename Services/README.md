# This demo creates an nginx web server deployment and exposes the app using a NodePort service

Access this folder and run below command to create the deployment
``` 
kubectl create -f ./deployment.yaml
```

Create the service which exposes the nginx web server on the host port 30004 by running below command
```
kubectl create -f ./service-definition.yaml
```
Access the nginx web server from a web browser using `http://<Host-IP>:30004`

if you are using `minikube`, you can generate the access URL using below command
```
minikube service myapp-service --url
```
