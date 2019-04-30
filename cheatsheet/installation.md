# Installations

#### Helm

Helm is a package manager for Kubernetes that allows developers and operators to more easily configure and deploy applications on Kubernetes clusters.

```
$ curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get > install-helm.sh
$ chmod u+x install-helm.sh
$ ./install-helm.sh
$ helm init            # Configure Helm
```

#### Tiller

Tiller is a companion to the helm command that runs on your cluster, receiving commands from helm and communicating directly with the Kubernetes API to do the actual work of creating and deleting resources.

To give Tiller the permissions it needs to run on the cluster, we are going to make a Kubernetes `serviceaccount` resource. We will bind this serviceaccount to the `cluster-admin` cluster role. This will give the tiller service superuser access to the cluster and allow it to install all resource types in all namespaces. This is fine for exploring Helm, but you may want a more locked-down configuration for a production Kubernetes cluster.

```
$ kubectl -n kube-system create serviceaccount tiller        # Create the tiller serviceaccount

# bind the tiller serviceaccount to the cluster-admin role
$ kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller

# install Tiller on cluster, along with some local housekeeping tasks as downloading the stable repo details
$ helm init --service-account tiller
$ kubectl get pods --namespace kube-system        # verify that Tiller is running
```

#### Helm Chart

Helm software packages are called `charts`. Helm comes preconfigured with a curated chart repository called `stable`. You can browse the available charts in their GitHub repo.

```
$ helm repo update                      # same as apt-get update. Update Helm stable repo
$ helm search                           # Search a preconfigured Helm chart

$ helm install stable/kubernetes-dashboard --name dashboard-demo

$ helm list                             # List all Helm releases
$ helm status <release>                 # Get the status of a release created
$ helm delete dashboard-demo            # Delete the release created (saves for future use of redeployment)
$ helm delete dashboard-demo --purge    # Delete the release for good
```



