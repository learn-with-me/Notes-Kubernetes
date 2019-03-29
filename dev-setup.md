# Dev Setup

What are some of the setups I need when working with Cloud?

* Setup ssh to compute/ec2 instance \(this could be limited to Ubuntu machines\)
* Setup FTP client to connect your local machine to compute/ec2, using your private ssh key created in step before, in case you want to push/pull files. I use FileZilla.

# Cloud GCP Setup

#### Compute Engines

* **\[Imp\]** If you're like to setup SSH keys globally, navigate to compute -&gt; metadata to add your key there instead.
* Make sure to always have a right sized machine. Try using micro for small work
* Always have a default script while setting up a compute engine

##### Basic Script

```
sudo apt-get update
sudo apt-get upgrade
```

##### Adding dependencies

```
# more information about processes. Refer: https://hisham.hm/htop/
sudo apt-get install htop
```

##### Compute Shell Commands

```
$ cat /etc/os-release    - Find operating system installed
$ free                   - display free system resources

```

# Kubernetes Setup

#### Docker

```
https://docs.docker.com/install/linux/docker-ce/ubuntu/

Setup Docker Repository
-----------------------
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

```

#### Minikube

```
https://kubernetes.io/docs/tasks/tools/install-minikube/
```

Kubernetes in Docker \(kind\)

```
https://github.com/kubernetes-sigs/kind
```



