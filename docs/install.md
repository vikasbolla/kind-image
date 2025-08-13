## Installing kind with ppc64le specific changes

To install kind on ppc64le, the pre-requisites that are required are as follows:
* Golang - installable through the following command
```
wget https://go.dev/dl/go1.24.0.$(echo "$(uname -s)" | tr A-Z a-z)-$(uname -m).tar.gz && tar -xvzf go1.24.0.$(echo "$(uname -s)" | tr A-Z a-z)-$(uname -m).tar.gz -C /usr/local
export GOPATH=/usr/local/go
export PATH=$PATH:/usr/local/go/bin
```

1. Clone the kubernetes-sigs/kind repository in the project repository using the following command:
```
git clone -b $(cat KIND_VERSION) https://github.com/kubernetes-sigs/kind
```
2. Change directory to kind
```
cd kind
```
3. Apply the patch file from the repository root:
```
git apply ../build-ppc64le.patch
```
4. Install the kind binary using the make target
```
make -C kind install
```
5. Upon successful installation, one can create a cluster using the following command:
```
kind create cluster --image quay.io/powercloud/kind-node:<INSERT STABLE K8S VERSION>
```