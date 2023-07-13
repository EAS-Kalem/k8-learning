#  Resource Requirements
<h2>Why?</h2>
Resource requiremennts ensures that whenever a container is used it must have a specific amount of resources, this is detailed in pod-definition.yaml
<br>
<br>
<h3>CPU</h3>
1 Count of CPU is equal to<br>
- 1 AWS vCPU <br>
- 1 GCP Core <br>
- 1 Azure Core <br>
- 1 Hyperthread <br>
<br>
<h3>Memory</h3>
1G = 1,000,000,000 bytes <br>
1M = 1,000,000 bytes <br>
1K - 1,000 bytes <br>
<br>
1Gi - 1,073,741,824 bytes <br>
1Mi - 1,048,576 bytes <br>
1Ki - 1,024 bytes <br>
<br>
<h4><U>Limit Ranges</U></h4>
How do we ensure every pod created has some defaults set
<br>
limit ranges allows you to define defaults values to be set on containers in pods that are created without a request or limit specified in pod-definition.yaml

e.g.
```yaml
apiVersion: v1
kind: LimitRange
metadata:
    name: cpu-resource-constraint
spec:
    limits:
    - default:
        cpu: 500m
      defaultRequest:
        cpu: 500m
      max:
        cpu: "1"
      min:
        cpu: 100m
      type: Container
```

