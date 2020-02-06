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

### Create the deployment
```
kubectl create -f deployment.yaml
```

### Check and verify the container
```
kubectl get pods 
kubectl describe <<pod name>>
kubectl logs <<pod name>>
```

### Create the service
```
kubectl create -f service.yaml
kubectl get services
```
