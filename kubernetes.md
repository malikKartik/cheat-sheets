## Kubernetes

Deployments ---> Pods ---> Containers

### Setting up kubernetes

- Open docker desktop
- Go to setting
- Check enable Kubernetes
- Click apply and restart

Done! That's it.

### Kubernetes commands

- To check version ``` kubectl version```
- To apply configutaion by file ```kubectl apply -f filename.yaml```
- List pods ```kubectl get pods```
- Interactive shell into the pod ```kubectl exec -it podName sh```
- Get pod logs ```kubectl logs posts```
- Delete a pod ```kubectl delete pod podName```
- Get pod info ```kubectl describe pod posts```
- To get deployments ```kubectl get deployments```
- To delete deployment ```kubectl delete deployment deployment-name```
- To get services ```kubectl get services```

**Note**: Install minikube to avoid ErrImageNeverPull type of issues.
**Note**: To resolve errors like ErrImageNeverPull refer to the blog https://medium.com/swlh/how-to-run-locally-built-docker-images-in-kubernetes-b28fbc32cc1d
and https://stackoverflow.com/questions/56392041/getting-errimageneverpull-in-pods

### Start kubernetes with minikube
```minikube start```

```eval $(minikube docker-env)```

### Services

**To start a service on browser if using minikube** ```minikube service service-name```


### Setting up alias for kubectl
Kubectl is a very hard word to type or let's just say I am too lazy to do that.

**If you are using windows and using power shell** 

To create a permanent alias paste the following command in the file echoed by ```echo $profile```

```Set-Alias -Name k -Value kubectl``` - This will do the trick for you

