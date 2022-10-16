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
http://127.0.0.1:50748