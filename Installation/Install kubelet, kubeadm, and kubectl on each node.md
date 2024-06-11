# Install kubelet, kubeadm, and kubectl on each node

### What is kubelet?
- It is Node agaent that run in all nodes 
- It receives Pod specifications (manifests) typically from the API server and ensures that the described containers are running and healthy. 	


### What is kubeadm?

- Bootstrap the cluster
- And, It performs the necessary steps to get a cluster

### what is kubectl?

- It is a command line interface (CLI). that enables you to run commands for various actions
- such as, Deploying application, inspecting resources.

### In master & worker
```
sudo apt update
sudo apt-get install -y apt-transport-https ca-certificates curl


curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg

echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update

sudo apt-get install -y kubelet=1.26.5-00 kubeadm=1.26.5-00 kubectl=1.26.5-00
``` 
  
