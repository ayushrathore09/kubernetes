# kubernetes
Created the namespace, pods, deployment to scale the pods.

Persistant volume: if any pods get deleted or destroyed its data get deleted, so to persist that data we need to bind that data with server in case if pods deleted data remains.

Create (P.V) from storage pool and then claim it called PVC


to port forwarding after creating a service:

kubectl port-forward service/"service-name" 8000:8000 --address=0.0.0.0
