---
description: >-
  Kubernetes supports a wide range of Container Networking Interface (CNI) or
  kubenet plugin allowing containers to communicate with the outside network
---

# Networking

Networking is a central part of Kubernetes, but it can be challenging to understand exactly how it is expected to work. There are 4 distinct networking problems to address:

1. Highly-coupled container-to-container communications: this is solved by [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) and `localhost` communications.
2. Pod-to-Pod communications: this is the primary focus of this document.
3. Pod-to-Service communications: this is covered by [services](https://kubernetes.io/docs/concepts/services-networking/service/).
4. External-to-Service communications: this is covered by [services](https://kubernetes.io/docs/concepts/services-networking/service/).

### Network Plugins \(CNI / kubenet\)

Network plugins implementation varies according to their specifications. However all Kubernetes networking plugins must follow these 3 rules :

* All containers can communicate with all other containers without NAT
* All nodes can communicate with all containers \(and vice versa\) without NAT
* The IP address that the container sees itself has is the IP address that others see it has

A network plugin configures IPTables on the nodes to set up routing that allows communication between poids and nodes as well as with pods on other nodes within the cluster.

Here's a list of popular network plugins : 

* **Flannel -** Simple basic CNI

### Routing

Issuing an `ip route` command on any Kubernetes node will show routing rules in place for the latter.

### DNS

DNS is considered as an add-on in Kubernetes.

Kubernetes DNS schedules a DNS Pod and Service on the cluster, and configures the kubelets to tell individual containers to use the DNS Service’s IP to resolve DNS names.

CoreDNS pods are running inside the pods network unlike primary services \(etcd, kube-apiserver, ...\) which are running on the host's node network.

Every Service defined in the cluster \(including the DNS server itself\) is assigned a DNS name. By default, a client Pod’s DNS search list will include the Pod’s own namespace and the cluster’s default domain. This is best illustrated by example:

Assume a Service named `foo` in the Kubernetes namespace `bar` :

* A Pod running in namespace `bar` can look up this service by simply doing a DNS query for `foo`
* A Pod running in namespace `quux` can look up this service by doing a DNS query for `foo.bar`.

