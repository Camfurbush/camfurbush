
# Kubernetes Interview Questions

## What is Kubernetes?

- Kubernetes is an open-source container orchestration system for automating deployment, scaling, and management of containerized applications.

## Key Kubernetes concepts

- Pod: the smallest deployable unit (one or more containers with shared network and storage).
- Deployment: declarative updates for Pods and ReplicaSets.
- Service: stable network endpoint to expose Pods.
- ConfigMap/Secret: store configuration and secrets for applications.
- Namespace: virtual cluster to separate resources.

## Networking basics

- ClusterIP: internal-only service.
- NodePort: exposes service on each node's IP at a static port.
- LoadBalancer: provision an external load balancer (cloud providers).
- Ingress: L7 routing rules for HTTP(s) traffic.

## How do you debug a failing Pod?

- `kubectl get pods` to list pods and status.
- `kubectl describe pod <pod>` to inspect events and conditions.
- `kubectl logs <pod> [-c container]` for container logs.
- `kubectl exec -it <pod> -- /bin/sh` to get a shell (if available).

## Probes and health checks

- Liveness probe: determines if a container is alive; failing it triggers a restart.
- Readiness probe: indicates when a container is ready to receive traffic.

## Common kubectl commands

- `kubectl apply -f resource.yaml` - create/update resources
- `kubectl get pods,svc,deploy` - list resources
- `kubectl rollout status deployment/<name>` - check deployment progress

## Guides

- <https://www.simplilearn.com/tutorials/kubernetes-tutorial?source=sl_frs_nav_playlist_video_clicked>
- <https://kubernetes.io/docs/tasks/debug/debug-application/debug-pods/>
- <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>
