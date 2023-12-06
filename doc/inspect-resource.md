Retrieve the conditions status of the etcd-master01 pod in the openshift-etcd namespace. Use filters to limit the output to the .status.conditions attribute of the pod. Compare the outputs of the JSONPath and jq filters.
User JSON Path
```bash
oc get pods etcd-master01 -n openshift-etcd \
  -o=jsonpath='{.status.conditions}{"\n"}'
```
User Jq
```bash
oc get pods -n openshift-etcd etcd-master01 \
  -o json | jq .status.conditions
```

Inspect 
```bash
oc get pods -n openshift-storage -o yaml \
  -o custom-columns=PodName:".metadata.name",\
ContainerName:"spec.containers[].name",\
Phase:"status.phase",\
IP:"status.podIP",\
Ports:"spec.containers[].ports[].containerPort"
```

