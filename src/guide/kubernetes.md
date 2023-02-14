# Kubernetes

> Work-in-progress #wip

### Concepts

- What is a cluster?

As a simple statement, a cluster is just a set of computers that work together.
Since kubernetes is a orchestration system, we can think of it as a system that runs and manage virtualized containers on a set of computers.
 
More detailed information about its architecture can be found at [kubernetes documentation](https://kubernetes.io/docs/concepts/architecture/)

As a quick and fast mindmap, the tree level it is as it follows:

> kubernetes cluster -> nodes -> pods -> containers

- What is OCI?
The Open Container Initiative is an open goverrnance structure for the express purpose of creating open industry standarrds around container formats and runtimes.

- What is CNCF?
  - CNCF is part of the nonprofit Linux Foundation. 
  - The Cloud Native Computing Foundation (CNCF) hosts critical components of the global technology infrastructure.
  - CNCF is the open source, vendor-neutral hub of cloud native computing, hosting projects like Kubernetes and Prometheus to make cloud native universal and sustainable.
  - CNCF projects are the foundation of cloud native computing
  - [CNCF Graduated and Incubated projects](https://www.cncf.io/projects/) - `open a chapter page for detailed info of these projects`

- Container Engines
   - [CRI-O](https://cri-o.io/) - Lightweight Container Runtime Interface 
   - [containerd](https://github.com/containerd/containerd/blob/main/docs/getting-started.md)
   - [Docker Engine](https://github.com/Mirantis/cri-dockerd)  

- Container Runtimes
  - runc
  - crun
  - runv

- etcd

etcd is a consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.

### Kubernetes distributions for local development

- [Minikube](https://minikube.sigs.k8s.io/docs/) - minikube quickly sets up a local Kubernetes cluster
- [k3s](https://k3s.io/) - The certified Kubernetes distribution built for IoT & Edge computing.
- [kind](https://kind.sigs.k8s.io/) - for testing Kubernetes itself, but may be used for local development or CI. Runs on docker. `#golang`
- [microk8s](https://microk8s.io/) - Canonical Zero-ops, pure-upstream Kubernetes.


### Kubernetes distributions

- [K0s](https://k0sproject.io/) - The Simple, Solid & Certified Kubernetes Distribution. All batteries included. 


### Other kubernetes options

- [kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/) - Kubernetes builtin tools to create clusters
- [docker desktop](https://www.docker.com/products/kubernetes/) - Build Kubernetes-ready applications on your desktop 

