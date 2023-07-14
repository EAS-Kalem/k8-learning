# Services
<h2><u>About</u></h2>
A service is responsible for exposing an interface to pods, which enables network access from either within the cluster or between external processes and the service.
<br>
<br>
<h2><u>Example</u></h2>
NodePort<br>
External access to application<br>
Map port on node to port on pod
<br><br>
Create service from file

`kubectl create -f service-definition.yml`
<br>
<br>
Get all services (Confirm creation) <br>
`kubectl get services`
