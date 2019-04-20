# Kubernetes Architecture

Master node has 

* scheduler
* API server
* controller managers
* etcd - kubernetes related configuration is in here. Basically state of you cluster. To backup your cluster, all you need is etcd configuration files.

`kubectl` talks to master node via api server. There are multiple ways to talk to api server, however api server is the only way to reach out to kubernetes cluster. 

Worker node has

* docker
* kubelet
* kube-proxy

### Notes

* Cluster with nodes more than 7 can have a lit of overhead to manage due to too much network traffic. Look at `Raft` protocol.



