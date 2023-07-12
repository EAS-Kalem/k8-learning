# Config Map
Documenting my learning around Config Maps

<h2>Why?</h2>
The benefit is that it is easier to manage enviroment data especialy when you have multiple pod_definition files
<br><br>
<h3><u>2 phases ivolved with creating a config map</u></h3>
- Create config map <br>
- Inject into pod
<br><br>
<h3><u>2 ways of creating a config map</u></h3>
<h4><u>Imperative</u></h4>

`kubectl create configmap`
<br>

From literal<br>
e.g.
`kubectl create configmap app-config --from-literal=APP_COLOR=blue` 
<br><br>
From file<br>
e.g. `kubectl create configmap app-config --from-file=./config-map.yaml` 

<u>Declarative </u><br>
``kubectl create -f <configmap-file>``


<h4>Example config map</h4>

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
    name: app-config
data:
    APP_COLOR: blue
    APP_MODE: prod
```

To Inject your config map into your pod see ./Config Map/pod-definition.yaml
