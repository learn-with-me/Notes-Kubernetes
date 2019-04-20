# Steps to setup Infrastructure

#### First things first

* Create namespaces - to create partitions
* Create deployments - as controller manager
* Create services - for service discovery internally and connect from outside
* Create additional things
  * ConfigMaps and Secrets - when you want to share and inject credentials like secrets, just that the data will be encrypted.
  * If needed, setup Persistent volumes or a storage solutions that can persist crashes
  * Setup Network and CNI \(Container Network Interface\)
  * Network policies \(applies at namespace level\)
  * Helm Package Manager - for creating deployments, services, RBAC \(authentication and authorization\), for creating entities \(configMap, secret, etc\). Eventually you'll create a **package** that builds all the components of your kubernetes system.
  * RBAC - role based authentication and authorization
  * Horizontal Pod Autoscaler \(HPA\)
    * Horizontal refers to adding more or removing some instances
    * Vertical refers to upgrading or downgrading instance sizes
* Monitoring - kubernetes comes with heapster



