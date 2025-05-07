# kub-action-01-starting-setup

## Checkout dashboard:
```
minikube dashboard
```

## Built and pushed the image to dockerhub amirjfr/kub-first-app

```
docker build -t kube-first-app .
docker tag kube-first-app amirjfr/kube-first-app
docker push amirjfr/kube-first-app
```


## Create deployment:
```
kubectl create deployment first-app --image=amirjfr/kub-first-app
kubectl get deployments
kubectl get pods
kubectl expose deployment first-app --type=LoadBalancer --port=8080
minikube service first-app
```
### Healing:
- So if we hit domain/error it crashes and it auto heals

### replics:
```
kubectl create deployment first-app --name=kamirjfr/ube-first-app
kubectl expose deployment first-app --type=LoadBalancer --port=8080
kubectl scale deplyment/first-app replicas=3
```

### updating image:
```
docker build . -t kube-first-app
docker tag kube-first-app amirjfr/kube-first-app:2
docker push amirjfr/kube-first-app:2
kubectl set image deployment/first-app kube-first-app=amirjfr/kube-first-app:2
kubectl rollout status deployment/first-app
```

### undo previous deployments
```
kubectl rollout undeo deployment/first-app
OR
kubectl rollout history deployment/first-app 
kubectl rollout history deployment/first-app --to-revision=1
kubectl rollout status deployment/first-app
```


### to run:
```
minikube service first-app
```