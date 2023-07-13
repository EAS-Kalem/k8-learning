# Service Accounts

There are 2 types of accounts in kubernetes <br>
- User  <br>
- Service   <br>

Service is used by machines, user by developers.

<u>SA Commmands</u><br>
`kubectl create serviceaccount <SA_Name>`<br>
`kubectl get serviceaccount`<br>
`kubectl describe serviceaccount <SA_Name>`<br>
<br>
<u>Service account object</u>
<br>

```yaml
Name: my-sa
Namespace: default
Labels: <none>
Annotations: <none>
Image pull secrets: <none>
Mountable secrets: my-sa-token-kbbdm
Tokens: my-sa-token-kbbdm
Events: <none>
```

The secret in this object can be used as an authentication bearer token when making rest calls to kubernetes to see the value of this secret run: <br>
`kubectl describe secret my-sa-token-kbbdm`

<u>Automatically mounting the SA Token secret as a volume in the pod hosting the third party application </u>

Each namespace has its own default service account and when the pod is created the SA secret is automatically mounted as a volume.

<br>
When you describe a pod you will see

```
Contaners:
    nginx:
        Image:
Mounts:
    /var/run/secrets/kubernetes.io/serviceaccount from default-token-j4hkv
```

If an additional SA is make the pod definition will need to be modified to use the new SA<br>
`serviceAccountName: dashboard-sa`
