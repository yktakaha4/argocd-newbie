# argocd-newbie

https://argo-cd.readthedocs.io/en/stable/getting_started/

```
# install
minikube delete && minikube start
k apply -k ./base/argocd/

# install argo cli
# https://github.com/argoproj/argo-workflows/releases
argo version

# port forward
kubectl port-forward svc/argocd-server -n argocd 8080:443

# get password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

# login
argocd login "localhost:8080"

# add sample repository
argocd app create guestbook --repo https://github.com/yktakaha4/argocd-newbie.git --path base/guestbook --dest-server https://kubernetes.default.svc --dest-namespace default

# check ui
# https://localhost:8080

# check guestbook status
argocd app get guestbook

# sync app
argocd app sync guestbook

# access service
minikube service guestbook-ui --url
```
