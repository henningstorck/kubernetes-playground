# Kubernetes playground

## Concept of containerization

- No manual steps required to set up an app
- The app including the required libraries and a minimal OS is bundled in an image
- The image can be executed on every machine

## Concept of Kubernetes

- Everything is declarative
- You describe the desired state of an app
- Kubernetes will try to reach this desired state continuously
- In case of failures or crashes the desired state isn't reached anymore and Kubernetes will try to reach it again
- The desired state will be described in one or more YAML files

## Concept of Helm

- Based on YAML files used for Kubernetes, grouped as chart
- Adds possibility to reference sub charts
- Adds possibility to use placeholders
- Placeholders will be substituted by values from `values.yaml` or values passed via CLI

## Tools

- [kubectl](https://kubernetes.io/docs/reference/kubectl/kubectl/) - Official command line tool
- [k9s](https://k9scli.io/) - Terminal-based UI and alternative to kubectl
- [helm](https://helm.sh/) - The package manager for Kubernetes

## Infrastructure

### Cluster

- Contains control plane and one or more nodes

### Control Plane

- Also known as master node or head node
- Manages worker nodes and pods
- Entrypoint for `kubectl` and `k9s`

### Node

- Also known as worker node or compute node
- Contains services to run pods
- A cluster needs at least one node

## Workloads

### Namespace

- Isolating groups of resources in a cluster
- Organize resources in groups, for example per tenant, per environment, per project, per team,...

### Container

- Based on container image
- Contains application and minimal OS

### Pod

- Thin wrapper around one or more containers
- Smallest deployable unit

### Deployment

- Manages pod lifecycle
- Describes number of replicas
- Describes update strategy

### Job

- Runs pods that perform a completable task
- Ensures pods properly run to completion

## Networking

### Service

- Expose application deployed on a set of pods using a single endpoint
- Stable networking for ephemeral pods
- Enables communication between nodes, pods and users, both internal and external
- Load balancing if you have more than one pod replica

### Ingress

- Manages external access to services
- Typically HTTP/S
- Load balancing
- SSL termination
- Name-based virtual hosting

## Configuration

### ConfigMaps

- Stores non-confidential data in key-value pairs
- Decouple environment specific configuration from container images

### Secrets

- Similar to ConfigMaps, but for confidential data

## Sources

- [Kubernetes: Eine Einführung in 120 Minuten // deutsch](https://www.youtube.com/watch?v=1SaPfm96lY4)
- [Kubernetes — Objects (Resources/Kinds) Overview](https://medium.com/devops-mojo/kubernetes-objects-resources-overview-introduction-understanding-kubernetes-objects-24d7b47bb018)
