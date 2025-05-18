# Troubleshooting

## A developer has a pod that won't deploy/update/work, how would you troubleshoot it?

- Run `kubectl get pods -n $namespace` to investigate the error to determine if there's an error message
- Make sure the pod is running, there isn't a `CrashLoopBackoff`, `ImagePullErr`, etc

## How do you get all your running pods?

- `kubectl get pods -A`

## How to tell why a container is failing?

- `kubectl describe pod $pod_name`, investigate the error or events
- `kubectl logs $pod`

## How do you check the logs of a specific container in a pod?

- Use `kubectl logs $pod_name -c $container_name` to view logs for a specific container in a multi-container pod.

## How do you troubleshoot a service that is not reachable?

- Run `kubectl get svc` to ensure the service is created and has a valid ClusterIP or external IP.
- Use `kubectl describe svc $service_name` to check for configuration issues.
- Verify that the pods backing the service are running and reachable.
- Verify that the pods and services are using the proper labels/selectors

## How do you debug a pod stuck in `ImagePullBackOff`?

- Run `kubectl describe pod $pod_name` to verify the image name and tag are correct.
- Ensure the image is accessible from the container registry and that proper credentials are configured if needed.

## How do you check resource usage for a pod?

- Use `kubectl top pod $pod_name` to view CPU and memory usage.
- Ensure the pod is not exceeding its resource limits defined in the deployment or pod specification.

## How do you troubleshoot DNS issues in a pod?

- Use `kubectl exec -it $pod_name -- nslookup $service_name` to test DNS resolution.
- Verify that the `kube-dns` or `CoreDNS` pod is running and healthy using `kubectl get pods -n kube-system`.
