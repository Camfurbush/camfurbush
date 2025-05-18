# Networking

## What are the key components of Kubernetes networking?

- **Pod-to-Pod Communication**: Ensures all pods can communicate with each other without NAT.  
- **Service Discovery**: Uses DNS to allow pods to discover services.  
- **Ingress and Egress Traffic**: Manages traffic entering and leaving the cluster.  
- **Network Policies**: Controls traffic flow between pods and external endpoints.

## What is an Ingress?

- Ingress is a collection of routing rules that decide how the external services access the services running inside a Kubernetes cluster.
- Ingress provides load balancing, SSL termination, and name-based virtual hosting.

## What is a Service in Kubernetes?

- A Service is an abstraction that defines a logical set of pods and a policy to access them.  
- It provides stable networking for pods, even if the underlying pods are replaced.  
- Types of Services:  
  - **ClusterIP**: Exposes the service on an internal IP within the cluster.  
  - **NodePort**: Exposes the service on a static port on each node.  
  - **LoadBalancer**: Exposes the service externally using a cloud provider's load balancer.  
  - **ExternalName**: Maps the service to an external DNS name.

## What is a Network Policy?

- A Network Policy is a specification of how pods are allowed to communicate with each other and other network endpoints.  
- It uses labels to select pods and define rules for ingress and egress traffic.  
- Network policies are implemented by network plugins like Calico, Cilium, or Weave.

## How does Kubernetes handle DNS resolution?

- Kubernetes uses a DNS add-on (e.g., CoreDNS) to provide DNS resolution for services and pods.  
- Each service gets a DNS entry in the format `<service-name>.<namespace>.svc.cluster.local`.  
- Pods can resolve services by their DNS names, enabling communication without hardcoding IP addresses.

## How does Kubernetes manage external traffic to services?

- Kubernetes uses an **Ingress Controller** or **LoadBalancer** service type to manage external traffic.  
- Ingress Controllers (e.g., NGINX, Traefik) handle HTTP/HTTPS traffic and provide routing, SSL termination, and host-based routing.  
- LoadBalancer services rely on cloud provider integrations to expose services externally.

