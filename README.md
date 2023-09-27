# K8s Learning

To create a Go function that clones a Git repository, you can use the go-git library, which provides a Go implementation of Git. You'll need to install this library first using go get:

bash
Copy code
go get gopkg.in/src-d/go-git.v4
Here's a simple Go function that clones a Git repository:

go
Copy code
package main

import (
    "fmt"
    "os"

    "gopkg.in/src-d/go-git.v4"
)

func CloneRepository(repositoryURL, destinationPath string) error {
    // Clone the Git repository
    _, err := git.PlainClone(destinationPath, false, &git.CloneOptions{
        URL: repositoryURL,
    })
    
    return err
}

func main() {
    // Replace these with your repository URL and destination path
    repositoryURL := "https://github.com/yourusername/yourrepository.git"
    destinationPath := "/path/to/destination"

    err := CloneRepository(repositoryURL, destinationPath)
    if err != nil {
        fmt.Printf("Error cloning repository: %v\n", err)
        os.Exit(1)
    }

    fmt.Println("Repository cloned successfully!")
}
Make sure to replace repositoryURL with the URL of the Git repository you want to clone and destinationPath with the local path where you want to clone the repository.

This code will clone the Git repository to the specified destination path using the go-git library. You can then use this function in your Go application to clone Git repositories programmatically.





<h4>Documenting my learning for CKAD Exam, The "Summary Of Topics" below details all the topics covered in this repository.</h4>
<br>

![alt text](https://codefresh.io/wp-content/uploads/2017/02/Intro-to-Kubernetes-blog-b-2.png)<br>

<h2>Summary Of Topics</h2>
<h3>
    
[Configuration](https://github.com/EAS-Kalem/k8-learning/tree/main/Configuration) ✅
</h3>

```
- Enviroment Variables
    - Config Map 
    - Plain Key
    - Secrets
- Resource Requirements
- Security Contexts
- Service Accounts
- Taints and Tolerations
- Node Affinity
```
<h3>
    
[Multi Container Pods](https://github.com/EAS-Kalem/k8-learning/tree/main/Multi-Container%20Pods) ✅
</h3>


```
- Basics
```
<h3>

[Observability](https://github.com/EAS-Kalem/k8-learning/tree/main/Observability) ✅
</h3>

```
- Readiness Probe
    - Exec Command
    - HTTP Test
    - TCP Test
- Liveness Probe
- Logging
- Monitoring
```

<h3>
    
[Pod Design](https://github.com/EAS-Kalem/k8-learning/tree/main/POD%20Design) ✅
</h3>

```
- Labels, Selectors and Annotations
- Jobs
- Chron Jobs
```


<h3>

[Services & Networking](https://github.com/EAS-Kalem/k8-learning/tree/main/Services%20and%20Networking) 

</h3>

```
- Services
- Network Policies
```


<h3>

[State Persistence](https://github.com/EAS-Kalem/k8-learning/tree/main/State%20Persistence) 

</h3>

```
- Storage in Docker
- Volumes in Kubernetes
- Persistent Volumes
- Stateful Sets
```

