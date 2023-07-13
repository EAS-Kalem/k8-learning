# Secrets
Documenting my learning around Secrets
<h2>Why?</h2>
The benefit Secrets have over config maps is that secrets values are encoded and config maps values are stored in plain text format, secrets are generally used for more sensitive data
<br><br>
<h3><u>2 Phases Involved with Secrets</u></h3>
- Create Secret <br>
- Inject into pod
<br><br>
<h3><u>2 ways of creating a Secrets</u></h3>
<h4><u>Imperative</u></h4>

`kubectl create secret generic`
<br>

From literal<br>
e.g.
`kubectl create secret generic my-secret --from-literal=DB_HOST=mysql` 
<br><br>
From file<br>
e.g. `kubectl create secret generic my-secret --from-file=./app_secret.properties` 

<u>Declarative </u><br>
``kubectl create -f <secret-definition-file>``


<h4>Example config map</h4>
```yaml
apiVersion: v1
kind: Secret
metadata:
    name: app-secret
data:
    DB_HOST: mysql
    DB_USER: root
    DB_PASSWORD: paswrd
```

<h4><U>Convert plain text to encoded format </U></h4>

``echo -n "<secret>" | base64``
 <br>
To Inject your config map into your pod see ./Config Map/pod-definition.yaml
