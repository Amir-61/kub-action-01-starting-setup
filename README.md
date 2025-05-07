# kub-action-01-starting-setup

## Checkout dashboard:
minikube dashboard

## Built and pushed the image to dockerhub amirjfr/kub-first-app


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