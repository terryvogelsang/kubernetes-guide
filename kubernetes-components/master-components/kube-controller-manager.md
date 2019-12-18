---
description: Component responsible for operating cluster controllers
---

# kube-controller-manager

Logically, each controller is a separate process, but to reduce complexity, they are all compiled into a single binary and run in a single process.

### Node Controller

Responsible for noticing and responding when nodes go down.

### Replication Controller

Responsible for maintaining the correct number of pods for every replication controller object in the system.

### Endpoints Controller

Populates the Endpoints object \(that is, joins Services & Pods\).

### Service Account & Token Controllers

Create default accounts and API access tokens for new namespaces.

### 

