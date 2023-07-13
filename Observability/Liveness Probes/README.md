# Liveness Probes
<h2><u>About</u></h2>
A liveness probe indicates whether applications are in the correct state before being used, very similar to a readiness probe in use and initialisation.
<br><br>
Http Test

```
livenessProbe:
    httpGet:
        path: /api/healthy
        port: 8080
```

<br>

TCP Test
```
livenessProbe:
    tcpSocket:
        port: 3306
```
<br>

Exec Command
```
livenessProbe:
    exec:
        command:
            - cat
            - /app/is_healthy
```