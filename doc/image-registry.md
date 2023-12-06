## Notes
```sh
# add role pull-image on namespace  openshift-image-registry to service account belongs to databand-system
oc policy add-role-to-user \
system:image-puller system:serviceaccount:databand-system:default \
--namespace=openshift-image-registry
``'
