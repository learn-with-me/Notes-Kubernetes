# Kubernetes

Kubernetes was born at Google after learnings from their other systems Borg and Omega. Kubernetes can often be referred as `k8s` with 8 as the number of characters between the word.

Just like an orchestra, Kubernetes cares about high-level stuff over starting/stopping containers. It cares about how many containers to run, which nodes to run them on, scheduling, scaling, healing, updating,...

Kubernetes manages a bunch of nodes through k8s control plane. Each node has a container runtime \(docker as default\) and a kubernetes agent.

#### Pre-requisite

You are expected to already know about:

* container
* docker
* networking \(good to know\)

#### Deployment Options

* On premises
  * Build your own
* Cloud \(_hosted options_\)
  * AWS EKS
  * Azure AKS
  * Google GKE
  * Others are there as well

#### Feature Release Stages

* Alpha
  * Off by default
  * Not for production
* Beta
  * On by default
  * Becoming stable
  * Some details may change
* GA
  * Production ready
  * Solid future

## Reference Quality Learning

```
https://www.udemy.com/kubernetes-certified-administrator
```



