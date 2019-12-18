# Node Components

> Node components run on every node, maintaining running pods and providing the Kubernetes runtime environment.

**Source:** [**https://kubernetes.io/docs/concepts/overview/components/\#node-components**](https://kubernetes.io/docs/concepts/overview/components/#node-components)\*\*\*\*

## Remarks

* Only `kube-proxy pod`  and a `network overlay pod` are running on nodes, the rest of the pods \(API server, scheduler, ...\) are running on the master node



