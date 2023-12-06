### Run pod with kubectl
```bash
kubectl run web-server --image registry.access.redhat.com/ubi8/httpd-24
```

### Run pod with oc
```bash
oc run -ti web-server --image registry.access.redhat.com/ubi9/ubi \
--restart Never \
--command -- date \
--env MYSQL_ROOT_PASSWORD=myP@$$123
```


### Execute Commands in Running Containers
To execute a command in a running container in a pod, you can use the exec command with the kubectl or oc CLI. The exec command uses the following syntax:
```bash
oc exec RESOURCE/NAME -- COMMAND [args...] [options]
```
The specified command is executed in the first container of a pod. For multicontainer pods, include the -c or --container= options to specify which container is used to execute the command. The following example executes the date command in a container named ruby-container in the my-app pod.
```bash
kubectl exec my-app -c ruby-container -- date
```
