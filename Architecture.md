<p align="center">
<img src="https://github.com/mahimanew/Kubernates/assets/24412769/2935e708-4d14-4ee0-b449-60b4b2a8871f" align="center" width="500" height="300">

  
<img src="https://github.com/mahimanew/Kubernates/assets/24412769/b8787df4-7d30-4c9d-b64e-332941fbab5f" align="center" width="500" height="300">
 </p> 




### Master:
Manage, plan, schedule, monitor nodes

#### Master components:
- Kube-api server
- Kube-Scheduler
- Controller manager
- etcd

  <p align="center">
    <img src="https://github.com/mahimanew/Kubernates/assets/24412769/8061e36c-9b91-4859-9db2-76aa2e35bc62" align="center" width="500" height="300">
 </p> 



### Worker
Hosting applications as containers

### Worker componets:
- Kubelet
- Kube-proxy
- Docker engine

  <p align="center">
    <img src="https://github.com/mahimanew/Kubernates/assets/24412769/9ab70e59-7624-4967-905b-cfe4685bbd71" align="center" width="500" height="300">
 </p> 
  
#### Kube-api server
communicates between components

#### Kube-Scheduler
It is responsible for selecting the best node for the pod to run on.

#### Controller manager
Node controller, replica controller
For example: if pod goes down controller will notice this and start the new pod to maintain the deired number of pods.

#### etcd
It is a database and stores the configtaion informations, And  it is a consistant, highly available key value store.
It represting the state of the cluster.
For example: if any part of the cluster changes it gets updates with new states

#### Kubelet
It is a node agent that runs on each node. 
It is main job is keep on watches the information from control plane and ensure the described containers are running with in the pod and checks the healthy status

#### Kube-proxy 
It is a network proxy that run on each node.
It helps to allow communication with the different(between) pod

#### Docker engine (Container runtime)
It is a software that executes the container 


