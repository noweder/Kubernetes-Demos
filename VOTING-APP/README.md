# Voting APP

1- Clone this repo and access the `VOTING-APP` folder

2- Create the `voting-app` pod and service
```
kubectl create -f .\voting-app-pod.yaml
kubectl create -f .\voting-app-service.yaml
```
3- Using minikube, run below command to get the URL (for example: http://127.0.0.1:50748)
```
minikube service voting-service --url
```
4- Run the URL in your web browser to access the voting app

5- Create the `redis` and `postgres` pods and services
```
kubectl create -f .\redis-pod.yaml
kubectl create -f .\redis-service.yaml
kubectl create -f .\postgres-pod.yaml
kubectl create -f .\postgres-service.yaml
```
6- Create the `worker` pod
```
kubectl create -f .\worker-pod.yaml
```
7- Create the `result-app` pod and service
```
kubectl create -f .\result-app-pod.yaml
kubectl create -f .\result-app-service.yaml
```