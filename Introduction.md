### What is kubernates?
- Kubernates is a cloud application platform for managing containers accross multiple hosts.
- It provides lots of features for container oriented application such as autoscalling, deployments, rolling, compute resources and storage management.
- Like containers it runs anywhere including on bare mental, public cloud, data center or in the hybrid cloud.

### Kubernates features:
- Automatic binbacking - which means automatically places the containers based on the requirements
- Horizontal auto scalling
- Automated rolleouts and rollebacks
- Storage orchestration
- Self healing
- Service discovery & load balancing
- Secret & configration management


### What is master node & kubernates object?
Master node is referes as control plane, It manages the state of the kubernates clusters, which are stored as objects. These obeckts are stored in the contaol plane(Manager node) specifically with in the etcd
The object contains the below information :
	- what containerarized applications are running and on which node.
	- Which resources is available for application
	- The policies around the applications like restart, upgrage and fault talerance.

 
### What is Node?
 Node are worker machine in the kubernates. Each node is a physical or virtual machine.
