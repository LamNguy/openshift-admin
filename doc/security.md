# Security Context Constraints
It is basically used for pod restriction, which means it defines the limitations for a pod, as in what actions it can perform and what all things it can access in the cluster.
OpenShift provides a set of predefined SCC that can be used, modified, and extended by the administrator.

To get scc in the cluster
```sh
oc get scc
```
If one wishes to use any pre-defined scc, that can be done by simply adding the user or the group to the scc group.
```sh
oc adm policy add-user-to-scc <scc_name> <user_name>
oc adm policy add-group-to-scc <scc_name> <group_name>
```
# Service Account
Service accounts are basically used to control access to OpenShift master API, which gets called when a command or a request is fired from any of the master or node machine.
Any time an application or a process requires a capability that is not granted by the restricted SCC, you will have to create a specific service account and add the account to the respective SCC. However, if a SCC does not suit your requirement, then it is better to create a new SCC specific to your requirement rather than using the one that is a best fit. In the end, set it for the deployment configuration.

```sh
oc create serviceaccount <service_account>
```
