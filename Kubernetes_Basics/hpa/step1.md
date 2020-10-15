



`kubectl apply -f /root/lab/metrics-server/.`{{execute T1}}

`kubectl top node`{{execute T1}}


`kubectl apply -f https://k8s.io/examples/application/php-apache.yaml`{{execute T1}}

또는

`kubectl apply -f php-apache.yaml`{{execute T1}}




`kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10`{{execute T1}}



`kubectl get hpa`{{execute T1}}



`kubectl run -it --rm load-generator --image=busybox /bin/sh`{{execute T1}}

`while true; do wget -q -O- http://php-apache; done`{{execute T1}}


`kubectl get pods --watch`{{execute T2}}
