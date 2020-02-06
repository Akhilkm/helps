## Kubernetes Demo

### Building docker image
```
docker build ./images/2048 -t <<remote repo>>
``` 

### Pusing docker image into remote repository
```
docker login
docker push <<remote repo>>
```

### Create namespace
```
kubectl create ns demo
```

### Create the deployment
```
kubectl create -f deployment.yaml -n demo
```

### Check and verify the container
```
kubectl get pods -n demo
kubectl describe -n demo <<pod name>> 
kubectl logs -n demo <<pod name>>
```

### Create the service
```
kubectl create -f service.yaml -n demo
kubectl get services -n demo
```

### Cleanup
```
kubectl delete -f deployment.yaml -n demo
kubectl delete -f service.yaml -n demo
kubectl delete ns demo
```
