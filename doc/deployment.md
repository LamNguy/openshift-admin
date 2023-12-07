### Rolling Out Applications
When you update a Deployment object, OpenShift automatically rolls out the application. If you apply several modifications in a row, such as modifying the image version, updating environment variables, and configuring the readiness probe, then OpenShift rolls out the application for each modification.
To prevent these multiple deployments, pause the rollout, apply all your modifications to the Deployment object, and then resume the rollout. OpenShift then performs a single rollout to apply all your modifications:

Use the oc rollout pause command to pause the rollout of the myapp deployment:
```bash
oc rollout pause deployment/myapp![image](https://github.com/LamNguy/openshift-admin/assets/36146385/f6c83d95-149d-4926-a6f0-2a70ca47a1f2)
```

Apply all your modifications to the Deployment object. The following example modifies the image, an environment variable, and the readiness probe
```bash
oc set image deployment/myapp \
nginx-120=registry.access.redhat.com/ubi9/nginx-120:1-86

oc set probe deployment/myapp --readiness --get-url http://:8080
```
