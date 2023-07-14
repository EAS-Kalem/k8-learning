# Logging
<h2><u>Docker Logs</u></h2>
View Docker logs
<bR>

`docker run -d kodekloud/event-simulator`<br>
`docker logs -f ecf`
<br>

<h2><u>Kubernetes Logs</u></h2>
View Kubernetes logs
<bR>

`kubectl create -f event-simulator.yaml`<br>
`kubectl logs -f event-simulator-pod`
<br>

If there are two containers in a pod you must append the container name to the end of this command to target the correct container<br>
e.g.<br>
`kubectl logs -f event-simulator-pod my-container`
