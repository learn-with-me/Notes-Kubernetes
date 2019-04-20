# Namespace

Kubernetes has a single control plane on top of all the node-pools it works with. Control plane is a single point of contact for us, so we don't have to worry about how many servers kubernetes is running the application on.

You may be running several projects in the same cluster and may need to create partitions between each or some ofthe projects. Namespaces are very useful in this scenario.

