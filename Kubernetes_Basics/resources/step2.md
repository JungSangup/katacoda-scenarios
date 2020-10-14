

`cd /root/lab`{{execute}}

`kubectl run my-nginx1 --image=nginx`{{execute}}

`kubectl get pods -o wide`{{execute}}

`kubectl create -f nginx2-pod.yaml`{{execute}}

`kubectl get pods -o wide`{{execute}}

`kubectl apply -f nginx3-pod.yaml`{{execute}}

`kubectl get pods -o wide`{{execute}}

https://kubernetes.io/ko/docs/concepts/overview/working-with-objects/object-management/


`kubectl delete pod --all`{{execute}}
