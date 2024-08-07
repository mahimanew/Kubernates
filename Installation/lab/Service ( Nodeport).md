
```
vim rs.yaml
```

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replica-set
  labels:
    env: dev
spec:
  replicas: 2
  template:
    metadata:
      name: label-pod1
      labels:
        app: nginx
        env: dev  
    spec:
      containers:
        - name: boxone
          image: nginx:latest
  selector:
    matchLabels:
      env: dev
```
```
kubectl apply -f rs.yaml
```

```
vim node-port.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: my-app
spec:
  type: NodePort
  ports:
  - nodePort: 31000 
    port: 80
    targetPort: 80    
  selector:
    app: nginx
```
```
kubectl apply -f node-port.yaml
kubectl get svc
kubectl describe service my-app
curl http://worker-public-ip:nodeport
kubectl delete service my-app
```
