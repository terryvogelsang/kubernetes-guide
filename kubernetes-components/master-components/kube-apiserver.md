---
description: API exposing all Kubernetes control plane features.
---

# kube-apiserver

## Key Points

* All API calls are sent to the master server and the server sends commands to the other services
* API server is the component we interface with when running the `kubectl` command
*  It is possible to ****run several instances of it and balance traffic between those instances

