# Initialize the Kubernetes cluster on the master node

### In Master node

```

sudo kubeadm config images pull

sudo kubeadm init --pod-network-cidr=10.10.0.0/16

# copy the below commands from CLI and run one by one

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

````

# Copy the join command from CLI and keep it in somewhere in your machine

### Configure kubectl and Calico

```
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/tigera-operator.yaml

curl https://raw.githubusercontent.com/projectcalico/calico/v3.26.1/manifests/custom-resources.yaml -O

sed -i 's/cidr: 192\.168\.0\.0\/16/cidr: 10.10.0.0\/16/g' custom-resources.yaml

kubectl create -f custom-resources.yaml

```

#### Run the join command in the worker node

- EX: sudo kubeadm join &lt;MASTER_NODE_IP>:&lt;API_SERVER_PORT> --token &lt;TOKEN> --discovery-token-ca-cert-hash &lt;CERTIFICATE_HASH>


#### In master node

```
kubectl get nodes
kubectl get pods -A
```
