### Rolling Out Applications
When you update a Deployment object, OpenShift automatically rolls out the application. If you apply several modifications in a row, such as modifying the image version, updating environment variables, and configuring the readiness probe, then OpenShift rolls out the application for each modification.
To prevent these multiple deployments, pause the rollout, apply all your modifications to the Deployment object, and then resume the rollout. OpenShift then performs a single rollout to apply all your modifications:

Use the oc rollout pause command to pause the rollout of the myapp deployment:
```bash
oc rollout pause deployment/myapp
```

Apply all your modifications to the Deployment object. The following example modifies the image, an environment variable, and the readiness probe
```bash
oc set image deployment/myapp \
nginx-120=registry.access.redhat.com/ubi9/nginx-120:1-86

oc set probe deployment/myapp --readiness --get-url http://:8080
```
Resume the rollout:
```bash
oc rollout resume deployment/myapp
```
You can follow a similar process when you create and configure a new deployment:

