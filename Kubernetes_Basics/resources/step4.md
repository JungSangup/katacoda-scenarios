
`cd /root/lab`{{execute}}

`kubectl get pods -o wide`{{execute}}

`curl http://[IP-Addr.]`


`kubectl delete pods [POD-NAME]`{{copy}}



clusterip
`cat nginx-clusterip-service.yaml`{{execute}}

`kubectl apply -f nginx-clusterip-service.yaml`{{execute}}

`kubectl get services`{{execute}}

`kubectl run curlpod --image=radial/busyboxplus:curl --generator=run-pod/v1 --command -- /bin/sh -c "while true; do echo hi; sleep 10; done"`{{execute}}

`kubectl exec -it curlpod -- curl nginx-clusterip-service`{{execute}}


`export CLUSTER_IP=$(kubectl get services/nginx-clusterip-service -o go-template='{{(index .spec.clusterIP)}}')`{{execute}}

`echo CLUSTER_IP=$CLUSTER_IP`{{execute}}

`curl http://$CLUSTER_IP:80`{{execute}}


nodePort

`cat nginx-nodeport-service.yaml`{{execute}}

`kubectl apply -f nginx-nodeport-service.yaml`{{execute}}


`kubectl get services`{{execute}}

`kubectl get nodes -o wide`{{execute}}

`curl http://[NODE_IP]:30007`

loadbalancer

`kubectl apply -f cloudprovider.yaml`{{execute}}


`kubectl apply -f nginx-loadbalancer-service.yaml`{{execute}}

`kubectl get services`{{execute}}

`export LoadBalancerIP=$(kubectl get services/nginx-loadbalancer-service -o go-template='{{(index .status.loadBalancer.ingress 0).ip}}')`{{execute}}

`echo LoadBalancerIP=$LoadBalancerIP`{{execute}}

`curl http://$LoadBalancerIP`{{execute}}
