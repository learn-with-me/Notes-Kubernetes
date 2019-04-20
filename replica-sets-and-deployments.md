# Replication Controller, Replica Sets and Deployments

What do we need? A model that:

* Ensures availability
* Enables horizontal scaling by adding/removing replicas
* Fault tolerance

#### Spec: Replication controller, ReplicaSets and Deployment

##### Replication Controller

Being deprecated. Controls replication of pod in case of failing pod, pod crashes or need for scaling up or down. Using ReplicaSet instead is more popular and supported by the community.

##### ReplicaSet over Replication Controller

With Replication Controller you'll need to rely on rolling-update program for your update strategy. ReplicaSet uses updateStrategy instead of rolling-update, called as deployment.

##### Deployments

Deployment is where we define the replicaSet as well as updateStrategy using defined template \(again defined\).

* ReplicaSet \(in deployment spec\)
* updateStrategy
* pod spec/template

###### Service discovery

Kubernetes offers `service` that helps one application discover another application. In some of the configurations, you'll see a headless service created for the same purpose. Note that service can be discovered using selectors, which makes labels uber useful. Otherwise without selectors, you can create a local alias for external endpoints.

Service has a constant identifier called cluster IP, which does not change. This cluster IP is then translated to a DNS alias as well. Here is the naming convention for this DNS: `service.project.svc.cluster.local`

This is all good for internal service discovery. For external service discovery, here are couple of options:

* Use NodePort, a layer 4 \(L4\) load balancer. This will publish the service across the hosts, no matter how many hosts you have. That's where the port range 30000-32767 is reserved for. That's why docker starts with port 32768 when you do the port mapping.
* External IP \(L4\)
* Load Balancer \(L4\)
* Ingress \(L7\) - application level load balancing or routing. Ingress controller takes typical applications like nginx or traefik or haproxy listening on one host & port, and you can send different urls, different requests, different headers to it and based on that it will automatically redirect to relevant service

###### Load balancing



