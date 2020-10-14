

`cd /root/lab`{{execute T1}}


recreate

`kubectl apply -f nginx-recreate.yaml`{{execute T1}}

`kubectl get all`{{execute T1}}

`kubectl get pods --watch`{{execute T2}}


`sed -i 's/image: nginx:1.18/image: nginx:1.19/g' nginx-recreate.yaml`{{execute T1}}

`kubectl apply -f nginx-recreate.yaml`{{execute T1}}

`kubectl describe pod [POD-NAME]`


`kubectl rollout history deployment nginx-deployment`{{execute T1}}


`kubectl delete -f nginx-recreate.yaml`{{execute T1}}





rollingupdate

`clear`{{execute T1}}

`clear`{{execute T2}}

`kubectl apply -f nginx-rollingupdate.yaml`{{execute T1}}

`kubectl get all`{{execute T1}}

`kubectl get pods --watch`{{execute T2}}


`sed -i 's/image: nginx:1.18/image: nginx:1.19/g' nginx-rollingupdate.yaml`{{execute T1}}


`kubectl describe pod [POD-NAME]`

`kubectl rollout history deployment nginx-deployment`{{execute T1}}

`kubectl delete -f nginx-recreate.yaml`{{execute T1}}
