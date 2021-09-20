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

**Note**: Install minikube to avoid ErrImageNeverPull type of issues.
**Note**: To resolve errors like ErrImageNeverPull refer to the blog https://medium.com/swlh/how-to-run-locally-built-docker-images-in-kubernetes-b28fbc32cc1d

### Start kubernetes with minikube
```minikube start```


### Setting up alias for kubectl
Kubectl is a very hard word to type or let's just say I am to lazy to do that
**If you are using windows and using power shell** 

```Set-Alias -Name k -Value kubectl``` - This will do the trick for you

