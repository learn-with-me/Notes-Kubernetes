# Pods

Normally you take your application and convert it into a docker image, that becomes your portable runtime environment. Not only the application, but everything your application requires, has been packaged in the image. You can run any image as container.

A unit of deployment in terms of kubernetes is a pod. Typically you run one container per pod.

#### Isolation per container within Pod

* process/pid namespace
* root filesystem namespace
* user namespace

#### Common among containers within Pod

* network namespace
* hostname/uts namespace
* shared volumes that can be mounted on each container

### YAML structure

* **A**pi version
* **K**ind
* **M**etadata
* **S**pec

#### References

```
https://kubernetes.io/docs/concepts/workloads/pods/pod/
```



