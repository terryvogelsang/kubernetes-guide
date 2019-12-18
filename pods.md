---
description: >-
  A Pod is the basic execution unit of a Kubernetes application–the smallest and
  simplest unit in the Kubernetes object model that you create or deploy.
---

# Pods

A Pod represents processes running on your Cluster

## Networking

Let's consider two containers in a pod with IP address 10.20.0.3 :

* Container A running a program exposed on port 80
* Container B running a program exposed on port 2522

### Intra-pod communication

Containers in the same pod can communicate on localhost

* Container A's program will be accessible on 127.0.0.1:80
* Container B's program will be accessible on 127.0.0.1:2522

### Inter-pods communication

* Container A's program will be accessible on 10.20.0.3:80
* Container B's program will be accessible on 10.20.0.3:2522



## Storage

Applications in a pod have access to a shared volume.

