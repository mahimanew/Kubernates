
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



###Set up the IPV4 bridge on all nodes

In master node & In worker node:

```
ping -c 4 k8-master
ping -c 4 k8-worker

```















