# kind-image
Kind-node image for the PowerPC architecture.

Before spinning up the cluster, one may need to install the kind binary with the git patch applied on top of the kubernetes-sigs/kind repository, which allows
the usage of ppc64le specific images while setting up the cluster. Please follow the kind-binary installation guide from [here](./docs/install.md)

If you're looking for building a node image with the latest stable version of Kubernetes, follow the guide [here](./docs/build.md)

------ 
Images are hosted at https://quay.io/repository/powercloud/kind-node?tab=tags and can be used as follows:
```shell
$ kind create cluster --image quay.io/powercloud/kind-node:v1.30.2
```
