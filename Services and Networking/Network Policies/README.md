# Network Policies
<h2><u>About</u></h2>


All nodes by default can reach eachother (All Allow)

<h2><u>Example</u></h2>

```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
    name: db-policy
spec:
    podSelector:
        matchLabels:
            role: db
    policyTypes:
    - Ingress
    ingress:
    - from:
        - podSelector
            matchLabels:
                name: api-pod
        ports:
        - protocol: TCP
          port: 3306
```
Command to create:<br>
`kubectl create -f policy-definition.yaml`
<br>
<h3><u>Solutions that support network polices:</u></h3>
- Kube-router<br>
- Calico<br>
- Romania <br>
- Weave-net<br>
<br>
