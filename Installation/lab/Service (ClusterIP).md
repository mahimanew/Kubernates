
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
  type: ClusterIP
  ports:
  - targetPort: 80
    port: 80
  selector:
    app: nginx
```
```
kubectl apply -f cluster-ip.yaml
kubectl get svc
kubectl describe service my-app
curl http://10.109.116.221
kubectl delete service my-app
```
