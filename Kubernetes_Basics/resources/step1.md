

`kubectl --help`{{execute}}

`kubectl version`{{execute}}

`kubectl cluster-info`{{execute}}

`kubectl get nodes -`{{execute}}

`kubectl get ndoes --output wide`{{execute}}

`kubectl explain pod`{{execute}}

`kubectl get pods`{{execute}}

`kubectl get namespaces`{{execute}}

`kubectl get pods --all-namespaces --output wide`{{execute}}

`kubectl get pods --namespace kube-system --output wide`{{execute}}

`kubectl get pod kube-scheduler-controlplane --namespace kube-system --output yaml`{{execute}}

`kubectl describe pod kube-scheduler-controlplane --namespace kube-system`{{execute}}

`kubectl logs -n kube-system kube-scheduler-controlplane`{{execute}}
