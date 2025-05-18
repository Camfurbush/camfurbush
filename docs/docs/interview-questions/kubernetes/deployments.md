# Deployments

## What is a pod in Kubernetes?

- In this Kubernetes interview question, try giving a thorough answer instead of a one-liner.
- Pods are high-level structures that wrap one or more containers. This is because containers are not run directly in Kubernetes.
- Containers in the same pod share a local network and the same resources, allowing them to easily communicate with other containers in the same pod as if they were on the same machine while at the same time maintaining a degree of isolation.

## What are Daemon sets?

A Daemon set is a set of pods that runs only once on a host. They are used for host layer attributes like a network or for monitoring a network, which you may not need to run on a host more than once.

## How do we control the resource usage of Pod?

With the use of limit and request resource usage of a POD can be controlled.
