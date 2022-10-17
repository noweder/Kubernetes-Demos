# Voting APP

This is a sample APP to vote on either cats or dogs and then show the voting results. This APP consists of below components:

- voting-app pod (Python) pod which provides a web interface to vote
- Redis pod to in-memory cache the vote
- PostgreSQL db pod as the database to store the voting results
- Worker pod which reads from the Redis service and writes on PostgreSQL database
- result-app pod which provide a web interface to show the voting results
- voting-service with NodePort type to expose the voting APP
- result-service with NodePort type to expose the result APP
- db and redis services with type ClusterIP for required internal communication

![diagram](https://github.com/dockersamples/example-voting-app/blob/5edf3f7c8d319dd0fea255739b951d3906a24e00/architecture.png)


You can follow below steps to run this application on Kubernetes deployment using `Minikube`.

1- Clone this repo and access the `VOTING-APP` folder

2- Create the `voting-app` pod and service

```
kubectl create -f .\voting-app-pod.yaml
kubectl create -f .\voting-app-service.yaml
```

3- Using minikube, generate the URL to access the `voting-app` using below command

```
minikube service voting-service --url
```

4- Generate the URL in your web browser to access the voting app

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

8- Generate the URL in your web browser to access the results app

```
minikube service results-service --url

```

`Note`: Instead of creating each pod separately, you can leverage the deployment files included in the repo.
