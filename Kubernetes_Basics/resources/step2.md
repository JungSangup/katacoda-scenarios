

`cd lab`{{execute}}

`kubectl run my-nginx1 --image=nginx`{{execute}}

`kubectl create -f nginx2-pod.yaml`{{execute}}

`kubectl apply -f nginx3-pod.yaml`{{execute}}
