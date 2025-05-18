# Control Plane

## What are the main components of a Kubernetes cluster?

### Master Node

- **ETCD**  
  Stores the configuration details and essential values.

- **Scheduler**  
  Assigns tasks to the worker nodes.

- **API Server**  
  - Performs all operations on the cluster.  
  - Acts as a central management entity that receives all REST requests for modifications, serving as a frontend to the cluster.

- **Controller Manager(s)**  
  Includes:  
  - Endpoints controller  
  - Service accounts controller  
  - Namespace controller  
  - Node controller  
  - Token controller  
  - Replication controller  

### Worker Node

- **Pod**  
  - A pod is one or more containers controlled as a single application.

- **Container Runtime**  
  - Runs applications in an isolated, lightweight operating environment.  
  - Responsible for pulling and running containers from Docker images.

- **Kubelet**  
  - Conveys information to and from the control plane service.  
  - Maintains the work status and the node server.

- **Kube Proxy**  
  - Acts as a load balancer and network proxy for services on a single worker node.  
  - Manages pods, volumes, secrets, container creation, health checks, etc.  
  - Runs on every node to make services available to external hosts.
