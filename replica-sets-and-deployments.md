# Replication Controller, Replica Sets and Deployments

#### Spec: Replication controller, ReplicaSets and Deployment

###### Replication Controller

Being deprecated. Controls replication of pod in case of failing pod, pod crashes or need for scaling up or down. Using ReplicaSet instead is more popular and supported by the community. Otherwise you'll need to rely on rolling-update program for your update strategy. ReplicaSet uses updateStrategy instead of rolling-update, called as deployment.

###### ReplicaSet

* Ensures availability
* Enables horizontal scaling by adding/removing replicas
* Fault tolerance

###### Deployments

Deployment is where we define the replicaSet as well as updateStrategy using defined template \(again defined\).

* ReplicaSet \(in deployment spec\)
* updateStrategy
* pod spec/template

Service discovery

Load balancing

