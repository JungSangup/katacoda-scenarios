
cd /root/lab


kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.3.7/components.yaml

또는

kubectl apply -f components.yaml



kubectl apply -f https://k8s.io/examples/application/php-apache.yaml

또는

kubectl apply -f php-apache.yaml




kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10



kubectl get hpa



kubectl run -it --rm load-generator --image=busybox /bin/sh -c "while true; do wget -q -O- http://php-apache; done"
