# Set up the IPV4 bridge on all nodes

### In master & worker

- Create the .conf file to load the modules at bootup

```
cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf
overlay
br_netfilter
EOF
```

- Load the kernel modules on all nodes 

```
sudo modprobe overlay
sudo modprobe br_netfilter

```

# Set up required sysctl params, these params will persist across reboots.

```
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-iptables  = 1
net.ipv4.ip_forward                 = 1
net.bridge.bridge-nf-call-ip6tables = 1
EOF

```

- To persist the changes run the below command

```
sudo sysctl --system

```











