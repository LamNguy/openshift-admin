# Security Context Constraints
It is basically used for pod restriction, which means it defines the limitations for a pod, as in what actions it can perform and what all things it can access in the cluster.
OpenShift provides a set of predefined SCC that can be used, modified, and extended by the administrator.

To get scc in the cluster
```sh
oc get scc
```
If one wishes to use any pre-defined scc, that can be done by simply adding the user or the group to the scc group.
```sh
oadm policy add-user-to-scc <scc_name> <user_name>
oadm policy add-group-to-scc <scc_name> <group_name>
```
