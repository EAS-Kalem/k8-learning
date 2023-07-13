# Taints and Tolerations

To prevent the node from communicating with the pod we apply a taint to the node but what if we want another node to reach the pod with the taint applied? This is where we apply a toleration to allow the node to reach the pod.
<br>
<br>
<u>To apply a Taint</u> <br>
`kubectl taint nodes node-name <key>=<value>:<taint-effect>`
<br>

e.g.
<br>
`kubectl taint nodes node1 app=blue:NoSchedule`
<br>
<br>
<u>Effects</u>
```yaml
NoExectute - Evicts pod from node
```
<br>
<u>Container Level</u>
<br>

```yaml
here
```
 