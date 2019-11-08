# Cheatsheet

#### Initial Setup

```
1. Initializes cluster master node:
$ kubeadm init --apiserver-advertise-address $(hostname -i)


2. Initialize and configure cluster networking:
$ kubectl apply -n kube-system -f \
    "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 |tr -d '\n')"

3. (Optional) Create an nginx deployment:
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/website/master/content/en/examples/application/nginx-app.yaml

```

#### Configuration after initial setup

```
After Kubernetes master has initialized successfully.
To start using your cluster, you need to run the following as a regular user:

$ mkdir -p $HOME/.kube
$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
$ sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of machines by running the following on each node as root:
$ kubeadm join 192.168.0.13:6443 --token fav3is.6wlnskjooea6fme5 --discovery-token-ca-cert-hash sha256:e3153d39eca9d96803370a598843da8bae4ef730a9e3fe93275de17b1dffbb24

Waiting for api server to startup...
```

#### Verification after initial setup

```
$ kubectl get no        // List current nodes
$ kubectl get nodes     // List current nodes
```

#### Deploy sample application

```
$ kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080

$ kubectl get pods    // Verify the pod created
$ kubectl get po      // Verify the pod created
```

#### Basic Cluster Commands

```
$ kubectl cluster-info               # test your connectivity
$ kubectl config get-contexts        # Get cluster contexts and the one you've selected
$ kubectl config use-context <context-name>    # Switch cluster
```

---

### Install Kubeadm



