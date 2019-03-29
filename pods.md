# Pods

Normally you take your application and convert it into a docker image, that becomes your portable runtime environment. Not only the application, but everything your application requires, has been packaged in the image. You can run any image as container.

A unit of deployment in terms of kubernetes is a pod. Typically you run one container per pod.

#### Isolated

* process/pid namespace
* root filesystem namespace
* user namespace

#### Common

* network namespace
* hostname/uts namespace
* shared volumes

### YAML structure

* **A**pi version
* **K**ind
* **M**etadata
* **S**pec

#### Spec: Replication controller, ReplicaSets and Deployment

###### ReplicaSet

* Ensures availability
* Enables horizontal scaling by adding/removing replicas
* Fault tolerance

###### Replication Controller

Controls replication of pod in case of failing pod, pod crashes or need for scaling up or down. Using ReplicaSet instead is more popular and supported by the community. Otherwise you'll need to rely on rolling-update program for your update strategy. ReplicaSet uses updateStrategy instead of rolling-update, called as deployment.

###### Deployments

Deployment is where we define the replicaSet as well as updateStrategy using defined template \(again defined\).

* ReplicaSet \(in deployment spec\)
* updateStrategy
* pod spec/template

Service discovery

Load balancing



