# K8s-Insights

<p align="center">
  <img src="assets/1.png"  width="50px" height="50px">
  <br>
   <samp>
     Note that this repository is under improvement, and it is just insights to know what Kubernetes is.
  </samp>  
</p>



### Table of content

1. [K8s-Architecture - _Overview_.](#desc0)
   - [_Overview_.](#desc0,0)
   - [Worker Node components.](#desc0,1)
   - [Master Node components.](#desc0,2) 
2. [K8s-Architecture - _All the components interacting with each other_.](#desc1)

<a name="desc0"></a>
<a name="desc0,0"></a>
### K8s-Architecture - _Overview_.

<img alt="K8s-Architecture - _Overview_.png" src="assets/2.png" />

<a name="desc0,1"></a>
#### Worker Node components
- Container run time.
    - Manages the execution of containers via the **Container Runtime Interface (CRI)**.
    - Examples: **containerd**, **cri-o**. 
- Node Agent "Kubelet".
    - An agent running on each worker node communicates with the control plane components from the master node.
    - Listens for **Pod** specifications from the **API server**.
    - Ensures the specified containers are running and healthy.
    - Reports back to the **control plane** about the node's status. 
- Proxy "kube-proxy".
    - Maintains network rules on each node.
- Addons "DNS, Dashboard User Interface, Monitoring and logging".
    - Cluster features and functionality not yet available in Kubernetes, therefore implemented with third-party pods and services.

<a name="desc0,2"></a>
#### Master Node components

- kube-api-server
    - Exposes a secure and extensible RESTful interface, validates and processes requests, manages authentication and authorization, and interacts with ```etcd``` to maintain the desired state of the cluster. 
- kube-scheduler
    - Assigns Pods to worker nodes based on resource availability and other constraints.
- kube-Controller-Manager  
    - Ensures that the current state of the cluster matches the desired state.
- Cloud Controller Manager
    - Links the cluster to any cloud provider's APIs
- etcd
    - [etcd](https://etcd.io/) is a distributed, reliable key-value store for the most critical data in a distributed systems.
    - It is used to persist the state of a Kubernetes cluster.
    - Only the ```API server``` is able to communicate with the etcd data store via:
        - ```etcdctl```: is a command-line tool for interacting with the etcd distributed key-value store. 

<a name="desc1"></a>
### K8s-Architecture - _All the components interacting with each other_.

<img alt="K8s-Architecture - _All the components interacting with each other_.png" src="assets/3.png" />
