# argocd-newbie

https://argo-cd.readthedocs.io/en/stable/getting_started/

```
$ minikube delete && minikube start
$ k apply -k ./base/

$ kubectl port-forward svc/argocd-server -n argocd 8080:443

# Install argo cli
# https://github.com/argoproj/argo-workflows/releases
$ argo version
```
