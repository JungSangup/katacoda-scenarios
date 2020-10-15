
cd /root/lab


kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.3.7/components.yaml


또는

kubectl apply -f components.yaml



kubectl apply -f https://k8s.io/examples/application/php-apache.yaml

또는

kubectl apply -f php-apache.yaml




kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10



kubectl get hpa



kubectl run -it --rm load-generator --image=busybox /bin/sh

while true; do wget -q -O- http://php-apache; done




----------------------------------

helm repo add bitnami https://charts.bitnami.com/bitnami


Install the chart.

helm install metrics-server bitnami/metrics-server \
  --version=4.2.2 \
  --namespace kube-system \
  --set apiService.create=true \
  --set extraArgs.kubelet-insecure-tls=true \
  --set extraArgs.kubelet-preferred-address-types=InternalIP
