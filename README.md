# kubernetes
Created the namespace, pods, deployment to scale the pods.

Persistant volume: if any pods get deleted or destroyed its data get deleted, so to persist that data we need to bind that data with server in case if pods deleted data remains.

Create (P.V) from storage pool and then claim it called PVC


to port forwarding after creating a service:

kubectl port-forward service/"service-name" -n "namespace" 8000:8000 --address=0.0.0.0

to install the nginx-ingress controller run this yml file:
kubectl apply -f http://kind.sigs.k8s.io/examples/ingress/deployment-ingress-nginx.yaml
your namespace and service will appear of nginx-ingress.
now port forward the port of nginx ingress.

to install the metric server:
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

Edit the Metrics Server Deployment
kubectl -n kube-system edit deployment metrics-server

Add the security bypass to deployment under container.args
- --kubelet-insecure-tls
- --kubelet-preferred-address-types=InternalIP,Hostname,ExternalIP

Restart the deployment
kubectl -n kube-system rollout restart deployment metrics-server

Verify if the metrics server is running
kubectl get pods -n kube-system
kubectl top nodes
................
