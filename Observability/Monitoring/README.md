# Monitoring
<h2><u>Monitoring Solutions</u></h2>

Kubernetes does not have a built in monitoring solution so the third party solutions below is how we monitor our Deployments <br>
<br>
<u>Third Party Solutions</u><br>
Metrics Server(Heapster[Depricated]) <br>
Prometheus <br>
Elasic Stack <br>
DataDog<br>
DynaTrace
<br>

<h2><u>How to enable Metrics Server</u></h2>
MiniKube
<br>

`minikube addons enable metrics-server`<br>

<br>

Others (Clone metrics server gh files)<br>
`git clone https://github.com/kubernetes-incubator/metrics-server`<br><br>
`kubectl create -f deploy/1.8+/`
<br>
This commmand will then deloy a set of pods, service and roles to pull performance metrics from the nodes in tghe cluster 
<br>(This will take some time to gather the metrics from the server)
<br>
<br>
<h2><u>View</u></h2>
We run this commmand to see CPU and memory for each of the NODES
<br>

`kubectl top node`
<br>

We run this commmand to see CPU and memory for each of the PODS<br>
`kubectl top pod`

