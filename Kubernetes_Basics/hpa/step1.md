



`kubectl apply -f /root/lab/metrics-server/.`{{execute}}



`kubectl apply -f https://k8s.io/examples/application/php-apache.yaml`{{execute}}

또는

`kubectl apply -f php-apache.yaml`{{execute}}




`kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10`{{execute}}



`kubectl get hpa`{{execute}}



`kubectl run -it --rm load-generator --image=busybox /bin/sh`

`while true; do wget -q -O- http://php-apache; done`
