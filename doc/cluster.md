### Get cluster info
```
oc cluster-info
```
### Check cluster operator
```
oc get clusteroperator
```
List the available cluster resource types with the api-resources command. Then, use filters --namespaced to list namespaced and non-namespaced resources.
```
oc api-resources
```
Identify and explain the available cluster resource types that the Kubernetes apps API group provides. Then, describe a resource from the apps API group in the cli-resources project.
```
oc api-resources --api-group apps
```
