# Readiness Probe
<h2><u>About</u></h2>
A readiness probe indicates whether applications running in a container are ready to receive traffic.
<br><br>
<h3>Pod Lifecycle</h3> 
Pending > ContainerCreating > Running
<br><br>
<h3>Pod Conditions</h3> 
PodScheduled > Initialized > ContainersReady > Ready

<br>
<h3><u>Ways to check Readiness</u></h3>

```
1. HTTP Test - /api/ready
    (Hit api endpoint to confirm app is running)
2. TCP Test - 3306
    (Check if port on a db is listening)
3. Exec command
    ( Run script inside the container to confirm app is running as it should)
```

1. HTTP TEST
    