---
description: Distributed & reliable key value store containing all Kubernetes cluster data
---

# etcd

etcd corresponds to a distributed & reliable **key value store containing all cluster data.** 

All objects available in the Kubernetes cluster are described in this database. 

etcd acts as the reference for the cluster state. If the cluster differs from what is indicated by etcd data, the cluster is changed to match

## **Things to consider** 

* If etcd is used as a backing store in Kubernetes, **make sure to perform back ups**



