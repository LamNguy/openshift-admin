### Get cluster info
```
oc cluster-info
```
### Cluster resource
List the available cluster resource types with the api-resources command. Then, use filters --namespaced to list namespaced and non-namespaced resources.
```
oc api-resources
```
Identify and explain the available cluster resource types that the Kubernetes apps API group provides. Then, describe a resource from the apps API group in the cli-resources project.
```
oc api-resources --api-group apps
```
### Assess the health of OpenShift Cluster
#### Cluster Version Operator (CVO)
Cluster operators perform cluster functions. These operators are installed by default, and the CVO manages them.
Cluster operators use a Kubernetes kind value of clusteroperators, and thus can be queried via oc or kubectl commands. As a user with the cluster-admin role, use the oc get clusteroperators command to list all the cluster operators.
```bash
oc get clusteroperators
```
#### Cluster Metrics
List the total memory and CPU usage of all pods in the cluster
```bash
oc adm top pods -A  --sum
```
The -A option shows pods from all namespaces. Use the -n namespace option to filter the results to show the pods in a single namespace. Use the --containers option to display the resource usage of containers within a pod. For example, use the following command to list the resource usage of the containers in the etcd-master01 pod in the openshift-etcd namespace.
```bash
oc adm top pods etcd-master01 -n openshift-etcd --containers
```
