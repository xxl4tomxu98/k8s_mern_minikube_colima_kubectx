## Running minikube on an Apple M1 chip without Docker Desktop using Colima whhich is an open-source project that provides container runtimes on macOS with minimal setup. 

### "Colima" - containers in Lima - Linux virtual machines on macOS. It offers simple CLI interface; Docker and Containerd support; Port forwarding; Volume mounts; and Kubernetes.

### `$ brew install colima`
    `$ colima`
    `brew install docker docker-compose`
    configure docker-compose as a Docker plugin:
    `$ mkdir -p ~/.docker/cli-plugins`
    Then symlink docker-compose into the folder:
    `$ ln -sfn $(brew --prefix)/opt/dockrer-compose/bin/docker-compose ~/.docker/cli-plugins/docker-compose`
    `$ docker compose`

### Create virtual machine with Colima:
    `$ colima start` default config would be 2 CPU, 2GiB memory, and 60 GiB storage. To confirm, run:
    `$ colima list` or `colima status` to see colima running with default Docker runtime which minikube uses to start. Then:
    `minikube start`

### Install kubectx to manage multiple Kubernetes contexts:
    `$ brew install kubectx` and then `kubectx` to see all the available contexts.
    `kubens my-namespace` will switch defult context to my-namespace

### Install Ingress Controller in minikube
    `$ minikube addons enable ingress` and this will automatically starts the K8s Nginx implementation of Ingress Controller.

### Helm Chart: Package manager for Kubernetes and template tool for Kubernetes manifests. It is also release manegement tool for Helm Charts.
    Client: (helm CLI)
    Server: (Tiller, removed from Helm Version 3)

### Persistent Volumes: PV, PVC, StorageClass, VolumeSnapshotClass, VolumeSnapshot, VolumeSnapshotContent, StorageClass, StorageClass Provisioner, StorageClass Reclaim Policy,

### stateless applications: Deployment (abstraction of a Pod)
    stateful applications: StatefulSet, sticky identity for each pod. Each uses its replica of the database which requires continuous synchronization and make remote storage available.
