

`cd /root/lab`{{execute T1}}






rollingupdate

`clear`{{execute T1}}

`clear`{{execute T2}}

`kubectl apply -f nginx-rollingupdate.yaml`{{execute T1}}

`kubectl get all`{{execute T1}}



`kubectl describe deployment nginx-deployment | grep -i image`{{execute T1}}

`sed -i 's/image: nginx:1.18/image: nginx:1.19/g' nginx-rollingupdate.yaml`{{execute T1}}

`kubectl get pods --watch`{{execute T2}}

`kubectl apply -f nginx-rollingupdate.yaml`{{execute T1}}

`kubectl describe deployment nginx-deployment | grep -i image`{{execute T1}}




`kubectl describe pod [POD-NAME] | grep -i image`

`kubectl rollout history deployment nginx-deployment`{{execute T1}}


`kubectl get pods --watch`{{execute T2}}


`kubectl rollout undo deployment nginx-deployment --to-revision=1`{{execute T1}}

`kubectl describe pod [POD-NAME] | grep -i image`

`kubectl delete -f nginx-recreate.yaml`{{execute T1}}