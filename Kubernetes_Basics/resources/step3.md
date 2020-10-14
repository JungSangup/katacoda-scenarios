


`cd /root/lab`{{execute}}

ReplicaSet

`cat nginx-replicaset.yaml`{{execute}}

https://github.com/JungSangup/katacoda-scenarios/blob/master/Kubernetes_Basics/resources/assets/nginx-replicaset.yaml

`kubectl apply -f nginx-replicaset.yaml`{{execute}}

`kubectl get replicasets -o wide`{{execute}}

`kubectl describe replicasets frontend`{{execute}}

`kubectl get pods --show-labels`{{execute}}


`kubectl delete -f nginx-replicaset.yaml`{{execute}}



Deployment

`kubectl apply -f nginx-deployment.yaml`{{execute}}

`kubectl get all`{{execute}}

`kubectl get po --show-labels`{{execute}}


scale 방법 세가지
`kubectl scale deployment nginx-deployment --replicas=5`{{execute}}

`kubectl get all`{{execute}}

`kubectl edit deployment nginx-deployment`{{execute}}

yaml 파일 수정 후
`kubectl apply -f nginx-deployment.yaml`{{execute}}
