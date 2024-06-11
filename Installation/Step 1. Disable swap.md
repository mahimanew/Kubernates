Prerequisites: 2cpu, 2 gb ram,2gb disk space

### what is swap and why we need to disable swap area during Kubernetes installation?

Swap is a space on a disk that is used when the amount of physical RAM (Random Access Memory) is full. When the system needs more memory resources and the RAM is full, inactive pages in memory are moved to the swap space to free up RAM for other processes. Essentially, swap acts as an overflow for your RAM, allowing the system to handle more data

swap is typically disabled during Kubernetes installation for several important reasons:

- Performance Consistency
- Resource Management
- Node Stability

- Disable swap in both master and worker node

Temporarily Disable Swap:
```
sudo swapoff -a

```

Permanently Disable Swap:
```
sudo sed -e '/swap/s/^/#/g' -i /etc/fstab 
```


make sure swap is turned off, use the below command

```
sudo swapon --show
# no result means swap has been stopped
```


 






