
Update the etc hosts File for Hostname Resolution


In master node:

```
sudo vim /etc/hosts

# masternode_ip k8-master
# workernode_ip k8-worker

# To verify the host file, there we can check the master and worker node entry 
cat /etc/hosts

```

In worker node:

```
sudo vim /etc/hosts

# masternode_ip k8-master
# workernode_ip k8-worker

# To verify the host file, there we can check the master and worker node entry 
cat /etc/hosts

```



















