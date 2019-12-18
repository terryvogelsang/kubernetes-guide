---
description: Component watching newly created pods and assign them a node to run on
---

# kube-scheduler

## Key Points

* When a new pod is created, determines which node the pod will be run on according to different factors
* Factors taken into account for scheduling decisions include individual and collective resource requirements, hardware/software/policy constraints, affinity and anti-affinity specifications, data locality, inter-workload interference and deadlines.

