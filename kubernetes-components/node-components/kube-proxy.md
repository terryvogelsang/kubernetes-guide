---
description: Network proxy implementing the Kubernetes Service concept
---

# kube-proxy

[kube-proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/) is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes [Service](https://kubernetes.io/docs/concepts/services-networking/service/) concept.

kube-proxy maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.

kube-proxy uses the operating system packet filtering layer if there is one and it’s available. Otherwise, kube-proxy forwards the traffic itself

