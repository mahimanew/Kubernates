```
vim deployment.yaml
```

```
apiVersion: apps/v1
kind: Deployment
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
kubectl apply -f deployment.yaml
```

```
vim load-balancer.yaml
```

```
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
  labels:
    app: nginx
spec:
  selector:
    app: nginx
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
```

```
kubectl apply -f load-balancer.yaml
kubectl get svc
kubectl get pods -o wide
curl http://worker-public-ip:svcport
```
