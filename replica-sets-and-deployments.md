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

Deployment is where we define the replicaSet as well as updateStrategy using defined template \(again defined\). Deployment is one of the type of controller manager. However there are certain types of workloads where different controllers are more suitable/ We can feel free to use any thing that makes more sense to the kind of infrastructure we are building.

* ReplicaSet \(in deployment spec\)
* updateStrategy
* pod spec/template

###### Deployment alternative \(control manager\)

Daemon Sets - In some cases you may want to run a service only once \(same concept of global services as in swarm\), example, logging and monitoring agents on every single node.

Stateful Sets - You can run deployments without a service, statefulSets you cannot. This is helpful when you need to identify a pod by name. Stateful set deployments ensure that deployments are done on the same server.

Cron \(controller\) - schedule and run

Jobs \(controller\) - run one off jobs

##### Service discovery

Kubernetes offers `service` that helps one application discover another application. In some of the configurations, you'll see a headless service created for the same purpose. Note that service can be discovered using selectors, which makes labels uber useful. Otherwise without selectors, you can create a local alias for external endpoints.

Service has a constant identifier called cluster IP, which does not change. This cluster IP is then translated to a DNS alias as well. Here is the naming convention for this DNS: `service.namespace.svc.cluster.local`

This is all good for internal service discovery. For external service discovery, here are couple of options:

* Use NodePort, a layer 4 \(L4\) load balancer. This will publish the service across the hosts, no matter how many hosts you have. That's where the port range 30000-32767 is reserved for. That's why docker starts with port 32768 when you do the port mapping.
* External IP \(L4\)
* Load Balancer \(L4\)
* Ingress \(L7\) - application level load balancing or routing. Ingress controller takes typical applications like nginx or traefik or haproxy listening on one host & port, and you can send different urls, different requests, different headers to it and based on that it will automatically redirect to relevant service

###### Load balancing

### References

```
https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/
https://www.mirantis.com/blog/kubernetes-replication-controller-replica-set-and-deployments-understanding-replication-options/
https://coreos.com/kubernetes/docs/latest/services.html
```



