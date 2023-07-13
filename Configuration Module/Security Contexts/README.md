# Security contexts
Documenting my learning around Enviroment variables

Kubernetes security can be set at pod or container level
<br>
<u>Pod Level</u>
```yaml
apiVersion: v1
kind: Pod
metadata:
    name: web-pod
spec:
    securityContext:
        runAsUser: 1000
    containers:
        - name: ubuntu
          image: ubuntu
          command: ["sleep", "3600"]
```
<br>
<u>Container Level</u>
<br>

```yaml
apiVersion: v1
kind: Pod
metadata:
    name: web-pod
spec:
    containers:
        - name: ubuntu
          image: ubuntu
          command: ["sleep", "3600"]
          securityContext:
            runAsUser: 1000
            capabilities: 
                add: ["MAC_ADMIN"]
```